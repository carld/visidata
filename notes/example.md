## Example usage

This version, 0.30, is 1300 lines of Python code that runs on both OS/X and
Linux without any external dependencies other than Python3.4.

Let''s look, for example, at the .tsv files generated by a previous project of mine, the [xd crossword corpus](http://xd.saul.pw):

- [puzzles.tsv] (9MB, 71k rows)
- [similar.tsv] (2MB, 72k rows)

    $ vd puzzles.tsv similar.tsv

Opens to the first of the sheets.

You can always press 'q' to quit any screen, but be careful; once quit, there is no way to get a sheet back.
'gq' quits all sheets (and the whole program).

### Header setup

I think if you''re going to distribute .csv or .tsv files, including a header
is best practice.  It''s all about data and metadata locality.  But headers are
not assumed in the default configuration, because there is no way to
bring the header row back down to the main set of rows.

But you can boost a row 'up' to the column names with '^' (current column only) or 'g^' (all columns).
You can also go to the 'C'olumns screen and 'e'dit the name of any columns.
'd' deletes the header row.

You could also go to the 'O'ptions sheet, '/' search for 'header', 'n'ext past the 'c_Header' (color scheme) to 'csv_header'.
'e'dit to 't'rue (or any value other than 0 or empty), 'q'uit back from options and '^R'eload the sheet.

### Sheet management

Go to the 'S'heets sheet, and select 'similar.tsv'.  Adjust the headers if needed, then go to the xdid (first) column and
press '!' to make it a key column.  Swap to the previous sheet ('puzzles') with ctrl-^ (like in vi), and make xdid a key column there too.

Go back to 'S'heets and notice the keyColNames is set for both these sheets.

's'elect both sheets (or use SPACE to toggle selection).  Notice the rows turn green.

Make sure that 'puzzles' is above 'similar', since it''s the primary table.
You can rearrange the sheets with 'J' and 'K' if need be.

Press '&' to combine the sheets (&=intersection, an inner join, only including rows that have matching keys in both sheets).

Could also do 

- 'plus' for an outer join (extend whatever keys in A with extra columns from B),
- 'star' for a full join (all rows from all sheets),
- 'tilde' for a diff join (all rows in A except those matching rows in B)

Press 'g_' (expand all columns to fit) to expand the name column.


We want to count the number of duplicates.

Move to the matchPct column.
Press '#' to convert column to integer.

- Press 'gs' to select all rows.
- Press '\' (unselect filter) then '^0' (regex) and 'Enter' to unselect rows starting with '0'.
- Press 'v' to hide the unselected rows.

### Tallying results

Move to xdid column.  Press 'gz' to group by it. [Alternately, can sort '{' by it and then just 'z' to group.]

Now we have one row per duplicate puzzle.  Add a column for the max matchPct:

        =len(matchPct)

Move over to this new column, and '}' sort descending.  'gk' or '<Home>' to go all the way to the top row.

### Joining the puzzles table again

Go to the column chooser and rename 'xdid' (press 'e' for edit on the cell) to 'laterXdid' (or anything else really), and 'matchXdid' to 'xdid'.

Now go to the sheet selector. Rename the puzzles&similar sheet to 'matches'.
Join 'matches' with the 'puzzles' sheet again (select nothing--inner).
Now there will be a 'puzzles&matches' sheet with 'later_Date', etc.
[Non-key fields with the same name as a field are prefaced with the sheet name].

### Cleaning up the output

Go to the column chooser.  Deselect (hide) any columns that are redundant or only add clutter.

Press 'q' to go back to the 'puzzles&matches' sheet.  Unselect '\later_Author != Author'.
'R'ead `queries/similarity.py` and use the 'boil()' function to make a better selection criteria.








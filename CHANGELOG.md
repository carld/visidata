# VisiData version history

## v0.92 (2017-07-11)
- `F`requency sheet groups numeric data into intervals
   - added `histogram_bins` and `histogram_even_interval` options
   - added `w` command on the sheet that toggles `histogram_even_interval`
- change key for 'eval Python expression as new pyobj sheet' from Ctrl-O to Ctrl-X

## v0.91 (2017-06-28)
- Make options automatically typed based on default
- Documentation cleanups
- Remove R command (set filetype on CLI)

## v0.80
- tour of screenshot.gif
- regex transform now `*` (';' is still regex split)
- Make regex search/select to work more like vim
- Move several non-essential commands out of vd.py
- change license of vd.py to MIT
- vdtutor start
- currency type with `$`; str type moved to `~`; remove type autodetect
- www/ for landing page
- move from .md to .rst for documentation

## v0.61 (2017-06-12)
- colorizers
- `g[` and `g]` to sort by all key columns
- `;` and `.` experimental regex commands

## v0.59 (2017-05-31)
- pivot sheets with `W`
- undo with `BACKSPACE` and replay with `ga`
- dev guide and user guide
- `ge` mass edit
- freeze with `g'`

## v0.44
- creating sustainable dev process at RC
- `z` scrolling prefix

## v0.42
- async select/unselect
- aggregator functions on columns
- .xls

## v0.41 (2017-01-18)
- asynchronous commands (each in its own thread) with
   - `^T` sheet of long-running commands
   - `^C` cancel
   - `ENTER` to see the final performance profile
- `P` random population of current sheet
- headerlines default now 1

## v0.40
- options settable with command-line arguments (`--encoding=cp437`)
- input() histories with UP/DOWN (and viewable with `I`)
- unicode input now works
- editText clears value on first typing
- `"` duplicates sheet with only selected rows; `g"` duplicates entire sheet verbatim

## v0.38
- sortable date
- open_zip comes back

## v0.37
- `g~` (autodetect all columns)
- `"` copies row to immediately following
- nulls, uniques on columns sheet

## v0.36
- right column
- regex subst
- unreverse [/] sort keys ([ = ascending)

## v0.35 (2016-12-04)
- reverse [/] sort keys
- goto `r`ow by number or `c`olumn by name

## v0.33
- type detection with `~`
- date type
- fix outer join

## v0.32
- expose col.type in column header
- push value conversion to time of usage/display

## v0.31
- F1 help sheet
- ^O directly exposes eval result as sheet
- custom editText with initial value, ESC that raises VEscape, and readline edit keys

## v0.30 (2016-11-27)
- make all sheets subclasses of VSheet
- remove .zip opening and url fetching
- added options ColumnStats and csv_header

## v0.29
- pin key columns to left
- join sheets on exact key match
- -r/--readonly mode

## v0.28 (2016-11-22)
- inputs: .csv, .tsv, .json, .hdf5, .xlsx, .zip
- outputs: .csv, .tsv
- hjkl cursor movement, t/m/b scroll to position screen cursor
- skip up/down columns by value
- row/column reordering and deleting
- resize column to fix max width of onscreen row
- filter/search by regex in column
- sort asc/desc by one column
- `g`lobal prefix supersizes many commands
- `e`dit cell contents
- convert column to int/str/float
- reload sheet with different format options
- add new column by Python expression
- `s`elect/`u`nselect rows, bulk delete with `gd`
- `F`requency table for current column with histogram
- `S`heets metasheet to manage/navigate multiple sheets,
- `C`olumns metasheet
- `O`ptions sheet to change the style or behavior
- `E`rror metasheet
- `g^P` status history sheet

## v0.14 (2016-11-13)



# Introduction

This is data from the Romanian Crosswords Competition. In the competition, the task is to fill a `13x13` crosswords grid with words and with at most `26` black points. Words can be chosen from two lists, called a "generic dictionary" and a "thematic dictionary". Every word from the thematic dictionary has a score equal to its length. Words from the generic dictionary have a score of 0. The objective is to maximize the score of the grid (i.e., the sum of all scores of the words). See [1] for a detailed description of the problem.

The data is shared with the permission of the Rebus publication, the publisher of the grids and the thematic lists.

# Folder structure

Besides this `README.md` file, three types of files are presented:
- A generic list of words (``dictionary'') in Romanian, in file `dictionary.txt`
- Thematic lists (dictionaries) for 9 years, in files `them-dic-YY.txt`, with `YY` representing a year in a two-digit format.
- Crosswords instances in files `inst-YYYY-NNN.pzl`. A file includes information such as the grid size, the configuration of black cells, the non-thematic dictionary (always `dictionary.txt`) and the thematic dictionary at hand. No letters are given in the grid in the instance files. In the instance file name, `YYYY` is a year an `NN` is a two-digit number from `00` to `11`. As such, for a given year, we give the instances extracted (after removing the letters) from the top 12 performers in that year. In each instance file, the thematic dictionary comes from that corresponding year. 

# Structure of instance files

Instance files have the following fields:
- The number of rows on the first line of the file
- The number of columns on the second line of the file
- Three numbers on one line each (placeholders)
- The grid on a number of lines (rows) in the file equal to the grid's number of rows. Each of these lines in the file has twice as many characters as the number of columns in the grid. Odd positions in the line are for the corresponding cell in the grid (blank for empty cells, `@` for a black cell). Even positions in the line are always blank. They are useful for an easy visualisation in a text file or text console. Their absence would make the grid very difficult to grasp, and this is especially true about grasping words in the grid going down vertically.
- A number specifying the number of dictionaries (always `2` in this dataset)
- For each dictionary, four lines in the file represent the following: a `1`/`0` flag for thematic or non-thematic; the filename of the dictionary; a flag whether the dictionary can be used for the across part (always `1`, i.e., `true` in this dataset); and a similar flag for the down part (always `1` in this dataset).

# References 

[1] A. Botea and V. Bulitko. 2021. Scaling Up Search with Partial Initial States in Optimization Crosswords. In Proceedings of the Symposium on Combinatorial Search, SoCS-21.

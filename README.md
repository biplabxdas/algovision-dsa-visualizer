# AlgoVision — Interactive DSA Visualizer

AlgoVision is a small browser project for seeing how sorting and searching algorithms work. The numbers are shown as bars, so you can watch them move while the algorithm runs.

**Built with:** HTML, CSS, and JavaScript

## Features

- Visualizes Bubble Sort, Selection Sort, and Merge Sort.
- Shows Binary Search on a sorted list.
- Lets you play, pause, step through, reset, or shuffle the animation.
- Displays counters for comparisons, swaps, writes, and search steps.

## Run the project

No setup or extra packages are needed.

1. Download or clone this repository.
2. Open `index.html` in a browser such as Chrome or Safari.
3. Choose an algorithm and use the controls to watch it run.

For Binary Search, enter a target number. The project sorts the list first because Binary Search only works correctly on sorted data.

## How the algorithms work

- **Bubble Sort:** Compares neighboring values and swaps them when they are out of order. Average and worst-case time: **O(n²)**. This version can stop early if a pass makes no swaps.
- **Selection Sort:** Finds the smallest value in the unsorted part and moves it into the next position. Time: **O(n²)**.
- **Merge Sort:** Splits the list into smaller parts, sorts them, and combines them. Time: **O(n log n)**. It uses extra space while merging.
- **Binary Search:** Checks the middle value and removes half of the remaining search range each time. Time: **O(log n)** on sorted data.

## About the counters

The counters show operations performed by the algorithms; they are not a speed benchmark. The animation pauses so each step can be seen, and that delay is separate from the algorithm's running time.

- **Comparisons:** Checks between values.
- **Swaps:** Pair exchanges during Bubble Sort and Selection Sort.
- **Writes:** Values copied back during Merge Sort.
- **Eliminated:** The number of unsuccessful Binary Search checks that discard part of the search range.

## Project files

- `index.html` contains the page structure and controls.
- `styles.css` controls the page layout and bar appearance.
- `app.js` contains the algorithms, animation controls, and counters.

## What this project helped me practice

Arrays, indexes, loops, swapping values, recursion, DOM updates, and Big O time complexity.

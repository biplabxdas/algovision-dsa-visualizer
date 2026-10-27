# AlgoVision — Interactive DSA Visualizer

A beginner-friendly, dependency-free browser app for exploring Bubble Sort, Selection Sort, Merge Sort, and Binary Search. It animates the values, supports play/pause and one-step-at-a-time playback, and tracks comparisons plus swaps, writes, or eliminated search boundaries.

## Run it on your MacBook Air M1

1. Open `index.html` in Safari or Chrome. No installation or account is needed.
2. Choose an algorithm. Use **Shuffle** for a new array, or **Play**, **Pause**, **Step**, and **Reset** to control it.
3. For Binary Search, enter a target. The visualizer sorts the array first because binary search requires sorted input.

Optional editor: install Visual Studio Code from [code.visualstudio.com](https://code.visualstudio.com) if you want a code editor. Node.js is not needed to run the app. It was already available on the setup machine, but this project has no build step or packages to install. Google Fonts are an optional visual enhancement; system fonts are used if the network is unavailable.

## What the counters mean

- **Comparisons:** value-to-value checks. Bubble and Selection Sort compare array elements. Merge Sort compares the front values of two sorted halves. Binary Search counts each middle-value check.
- **Swaps:** actual pair exchanges in Bubble and Selection Sort.
- **Writes:** values written back into the array during Merge Sort, including leftover values when one half runs out.
- **Eliminated:** Binary Search increments this once after each unsuccessful check to represent a discarded search half. It counts elimination rounds, not the number of array values removed.

These are teaching counters for this implementation, not a universal benchmark. The UI delay is for animation; it is not part of algorithm runtime.

## Concepts to learn

1. **Array and index:** `values` stores numbers; an index is a zero-based position. The screen labels use human-friendly one-based positions in the search messages.
2. **Loops:** sorting algorithms repeat comparisons over the array. Their loop bounds determine how many checks can happen.
3. **Swap:** `[values[i], values[j]] = [values[j], values[i]]` exchanges two positions without a temporary variable.
4. **Divide and conquer:** Merge Sort recursively splits the array, then merges sorted pieces. It takes O(n log n) time and O(n) auxiliary space.
5. **Search invariant:** Binary Search keeps a range `[low, high]` that can still contain the target. Each middle check halves that range, so it takes O(log n) time on sorted data.
6. **Complexity:** O(n²) means work grows roughly with the square of input size; O(n log n) grows more slowly; O(1) auxiliary space means constant extra storage; O(n) means extra storage proportional to input size.
7. **Async animation:** the algorithms pause at `checkpoint()` so a person can see each operation. That delay only affects the visualization.

## Interview prep notes

### Bubble Sort

“I compare adjacent values and swap them if they are out of order. After one full pass, the largest unsorted value has bubbled to the end. Average and worst-case time are O(n²); this implementation can finish early when a pass makes no swaps. It uses O(1) extra space.”

### Selection Sort

“For each position, I scan the remaining suffix for its minimum and swap that minimum into place. It does O(n²) comparisons even on sorted input, with at most n−1 swaps. It is in-place with O(1) extra space.”

### Merge Sort

“I recursively split the array until the pieces have one item, then merge sorted pieces by repeatedly taking the smaller front item. Its time is O(n log n), and this implementation uses O(n) temporary arrays. It is stable because equal items are taken from the left half first.”

### Binary Search

“On a sorted array, I inspect the middle value. If it is too small, I discard the left half; if too large, I discard the right half. The remaining candidate interval shrinks by about half per comparison, giving O(log n) time and O(1) extra space in this iterative version.”

### How to explain this project

“I built a browser-based visualizer with plain HTML, CSS, and JavaScript. I separate the interface from the algorithm logic, then render the array as bars. Each algorithm updates comparison and operation counters and pauses at checkpoints to make the state visible. I added Binary Search with a sorted input and a visible target, and I show each algorithm’s time and space complexity.”

Be ready to describe the code, not just repeat the summary. Try changing an algorithm’s loop bounds or the sorted input, predict what should change, and then run it to check your understanding.

## Suggested learning plan

| Session | Focus | Outcome |
|---|---|---|
| 1 (45–60 min) | Open the app, inspect HTML/CSS, learn array/index and DOM basics | Explain how a number becomes a bar |
| 2 (60–90 min) | Trace Bubble Sort by hand, then follow its loops and swap | Explain the pass and O(n²) behavior |
| 3 (60–90 min) | Trace Selection Sort and compare its swaps with Bubble Sort | Explain the minimum scan |
| 4 (90–120 min) | Draw Merge Sort split/merge steps, then inspect recursion | Explain O(n log n), stability, and extra space |
| 5 (60–90 min) | Trace Binary Search for found and absent targets | Explain sorted-input requirement and O(log n) |
| 6 (45–60 min) | Rebuild one algorithm from memory and practice interview explanation | Describe design choices and trade-offs confidently |

Estimated total: about **6–8 hours**, spread across a few days. Ask an AI assistant to explain one function at a time, trace a small input (for example `[7, 3, 5]`), and quiz you after you predict each step. Avoid accepting a change until you can explain it back in your own words.

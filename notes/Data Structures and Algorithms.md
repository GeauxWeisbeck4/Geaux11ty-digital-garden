- 
- 
- ## From Colt Steele's Course
    - # Recursion
        - ```javascript
function collectOdds (arr) {
          let newArr = []
          if (arr.length === 0) return newArr

          if (arr[0] % 2 !== 0) {
            newArr.push(arr[0])
          }

          newArr = newArr.concat(collectOddValues(arr.slice(1)))
          return newArr
        }
        
        collectOdds([1, 2, 3, 4, 5, 6, 7, 8, 9])
        // 1, 3, 5, 7, 9```
    - # Algorithms
        - ## Linear Search
        - ```javascript
function linearSearch(arr, val) {
          for (let i = 0; i < arr.length; i++) {
            if (arr[i] == val) return i
          }
          return -1
        }

        linearSearch([34, 56, 1, 2], 56)
        // 1
      ```
        - ## Binary Search
        - ```javascript
function binarySearch(arr, elem) {
          let start = 0
          let end = arr.length - 1
          let middle = Math.floor((start + end) / 2)

          while (arr[middle] !== elem && start <= end) {
            elem < arr[middle] ? (end = middle - 1) : (start = middle + 1)
            middle = Math.floor((start + end) / 2)
          }
          return arr[middle] === elem ? middle : -1
        }
      
        binarySearch([2, 5, 6, 9, 13, 15, 28, 30], 9) // 3
        binarySearch([2, 5, 6, 9, 13, 15, 28, 30], 50) // -1```
        - ## Bubble Sort
        - ```javascript
function bubbleSort(arr) {
          const swap = (arr, idx1, idx2) =>
            ([arr[idx1], arr[idx2]] = [arr[idx2], arr[idx1]])

          let noSwaps
          for (let i = arr.length; i > 0; i--) {
            noSwaps = true
            for (let j = 0; j < i - 1; j++) {
              if (arr[j] > arr[j + 1]) {
                swap(arr, j, j + 1)
                noSwaps = false
              }
            }
            if (noSwaps) break
          }
          return arr
        }

        bubbleSort([37, 45, 29, 8, 12, 88, -3])
        // -3, 8, 12, 29, 37, 45, 88
      ```
        - ## Selection Sort
        - ```javascript
function selectionSort(arr) {
          const swap = (arr, idx1, idx2) =>
            ([arr[idx1], arr[idx2]] = [arr[idx2], arr[idx1]])

          for (let i = 0; i < arr.length; i++) {
            let lowest = i
            for (let j = i + 1; j < arr.length; j++) {
              if (arr[j] < arr[lowest]) {
                lowest = j
              }
            }
            if (i !== lowest) swap(arr, i, lowest)
          }
          return arr
        }

        selectionSort([0, 2, 34, 22, 10, 19, 17])
        // 0, 2, 10, 17, 19, 22, 34
      ```
        - ## Insertion Sort
        - ```javascript
function insertionSort(arr) {
          for (let i = 1; i < arr.length; i++) {
            let currentVal = arr[i]
            for (var j = i - 1; j >= 0 && arr[j] > currentVal; j--) {
              arr[j + 1] = arr[j]
            }
            arr[j + 1] = currentVal
          }
          return arr
        }

        insertionSort([2, 1, 9, 76, 4])
        // 1, 2, 4, 9, 76
      ```
        - ## Merge Sort
        - ```javascript
function merge(arr1, arr2) {
          let results = []
          let i = 0
          let j = 0

          while (i < arr1.length && j < arr2.length) {
            if (arr2[j] > arr1[i]) {
              results.push(arr1[i])
              i++
            } else {
              results.push(arr2[j])
              j++
            }
          }
          while (i < arr1.length) {
            results.push(arr1[i])
            i++
          }
          while (j < arr2.length) {
            results.push(arr2[j])
            j++
          }

          return results
        }

        // merge([1, 10, 50], [2, 14, 99, 100])

        // recursive
        function mergeSort(arr) {
          if (arr.length <= 1) return arr
          let mid = Math.floor(arr.length / 2)
          let left = mergeSort(arr.slice(0, mid))
          let right = mergeSort(arr.slice(mid))
          return merge(left, right)
        }

        mergeSort([10, 24, 76, 73, 72, 1, 9])
        // 1, 9, 10, 24, 72, 73, 76```

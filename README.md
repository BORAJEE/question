# question
Write a program that takes as input a sorted array of numbers. The objective is to return the array arranged in an
alternate order such that max value is followed by min value in a descending fashion, so that the 1st element is the
max value, 2nd element is the min value, 3rd element is the second max value, 4th element is the second min value &
so on.
Example: For an input array [2, 4, 6, 8, 10],
the expected result would be [10, 2, 8, 4, 6]

<script>
 
// JavaScript program to rearrange an array in minimum
// maximum form
 
// Prints max at first position, min at second position
// second max at third position, second min at fourth
// position and so on.
function rearrange(arr, n)
{
    // Auxiliary array to hold modified array
    let temp = new Array(n);
 
    // Indexes of smallest and largest elements
    // from remaining array.
    let small = 0, large = n - 1;
 
    // To indicate whether we need to copy remaining
    // largest or remaining smallest at next position
    let flag = true;
 
    // Store result in temp[]
    for (let i = 0; i < n; i++) {
        if (flag)
            temp[i] = arr[large--];
        else
            temp[i] = arr[small++];
 
        flag = !flag;
    }
 
    // Copy temp[] to arr[]
    for (let i = 0; i < n; i++)
        arr[i] = temp[i];
}
 
// Driver code
    let arr = [ 1, 2, 3, 4, 5, 6 ];
    let n = arr.length;
 
    document.write("Original Array<br>");
    for (let i = 0; i < n; i++)
        document.write(arr[i] + " ");
 
    rearrange(arr, n);
 
    document.write("<br>Modified Array<br>");
    for (let i = 0; i < n; i++)
        document.write(arr[i] + " ");
 
</script>

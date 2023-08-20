# ceilingProblemBinarySearch
import java.util.Scanner;
import java.util.Arrays;

public class ceilingQuestionBinarySearch {
    public static void main(String[] args) {
        System.out.println("enter the size of array : ");
        Scanner sc = new Scanner(System.in);
        int size = sc.nextInt();
        int arr[] = new int[size];
        System.out.println(" enter elements of array");
        for (int i = 0; i < size; i++) {
            arr[i] = sc.nextInt();
        }
        Arrays.sort(arr);
        System.out.println("sorted array is : ");
        System.out.println(Arrays.toString(arr));
        System.out.println("enter the targeted element : ");
        int target = sc.nextInt();
        int index = binarySearch(arr, target);
        System.out.println(index);
        System.out.println("Ceiling  Element is :");
        System.out.println(arr[index]);

    }

    static int binarySearch(int[] arr, int target) {
        // if the target is greater than the greatest number int the array
        if (target > arr[arr.length - 1]) {
            return -1;
        }
        int start = 0;
        int end = arr.length - 1;
        while (start <= end) {
            // int mid = (start + end) /2 ;
            int mid = start + (end - start) / 2;
            if (target < arr[mid]) {
                end = mid - 1;
            } else if (target > arr[mid]) {
                start = mid + 1;
            } else {
                return mid;
            }

        }
        return start;
    }
}

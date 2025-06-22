import java.util.Scanner;

public class ArrayOperations {
    
    // Method to sort array using bubble sort
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n-1; i++) {
            for (int j = 0; j < n-i-1; j++) {
                if (arr[j] > arr[j+1]) {
                    // swap arr[j] and arr[j+1]
                    int temp = arr[j];
                    arr[j] = arr[j+1];
                    arr[j+1] = temp;
                }
            }
        }
    }

    // Method to find second lowest and second highest numbers
    public static void findSecondLowestAndHighest(int[] arr) {
        int secondLowest = -1, secondHighest = -1;
        int n = arr.length;

        // Assume array is already sorted
        for (int i = 1; i < n; i++) {
            if (arr[i] != arr[0]) {
                secondLowest = arr[i];
                break;
            }
        }

        for (int i = n - 2; i >= 0; i--) {
            if (arr[i] != arr[n - 1]) {
                secondHighest = arr[i];
                break;
            }
        }

        System.out.println("Second Lowest: " + secondLowest);
        System.out.println("Second Highest: " + secondHighest);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int[] numbers = new int[5];

        System.out.println("Enter 5 different numbers:");
        for (int i = 0; i < 5; i++) {
            System.out.print("Number " + (i + 1) + ": ");
            numbers[i] = sc.nextInt();
        }

        bubbleSort(numbers);

        System.out.print("Sorted Array: ");
        for (int num : numbers) {
            System.out.print(num + " ");
        }
        System.out.println();

        findSecondLowestAndHighest(numbers);
    }
}

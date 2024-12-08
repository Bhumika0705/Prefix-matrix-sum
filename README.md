# Prefix-matrix-sum
sum of prefix matrix
import java.util.Scanner;

public class prefixmatrixsum {
    public prefixmatrixsum() {
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the dimensions of array:");
        int n = sc.nextInt();
        int m = sc.nextInt();
        int[][] mat = new int[n][m];
        System.out.println("Enter the elements of array:");

        int i;
        for(int i = 0; i < n; ++i) {
            for(i = 0; i < m; ++i) {
                mat[i][i] = sc.nextInt();
            }
        }

        int[][] arr = new int[n][m];

        for(i = 0; i < n; ++i) {
            for(int j = 0; j < m; ++j) {
                arr[i][j] = mat[i][j];
                if (i != 0 || j != 0) {
                    if (i == 0) {
                        arr[i][j] += arr[i][j - 1];
                    } else if (j == 0) {
                        arr[i][j] += arr[i - 1][j];
                    } else {
                        arr[i][j] += arr[i - 1][j] + arr[i][j - 1];
                    }

                    for(i = 0; i < n; ++i) {
                        for(j = 0; j < m; ++j) {
                            System.out.println(arr[i][j] + " ");
                        }
                    }
                }
            }

            System.out.println();
        }

    }
}

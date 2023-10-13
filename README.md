public class MatrixOperations {
    public static void main(String[] args) {
        int[][] matrixA = {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        
        int[][] matrixB = {
            {9, 8, 7},
            {6, 5, 4},
            {3, 2, 1}
        };

        int[][] resultMatrix = addMatrices(matrixA, matrixB);
        System.out.println("Matrix A + Matrix B:");
        printMatrix(resultMatrix);

        resultMatrix = multiplyMatrices(matrixA, matrixB);
        System.out.println("Matrix A * Matrix B:");
        printMatrix(resultMatrix);
    }

    // Function to add two matrices
    public static int[][] addMatrices(int[][] A, int[][] B) {
        int rows = A.length;
        int columns = A[0].length;
        int[][] result = new int[rows][columns];

        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < columns; j++) {
                result[i][j] = A[i][j] + B[i][j];
            }
        }

        return result;
    }

    // Function to multiply two matrices
    public static int[][] multiplyMatrices(int[][] A, int[][] B) {
        int rowsA = A.length;
        int columnsA = A[0].length;
        int columnsB = B[0].length;
        int[][] result = new int[rowsA][columnsB];

        for (int i = 0; i < rowsA; i++) {
            for (int j = 0; j < columnsB; j++) {
                for (int k = 0; k < columnsA; k++) {
                    result[i][j] += A[i][k] * B[k][j];
                }
            }
        }

        return result;
    }

    // Function to print a matrix
    public static void printMatrix(int[][] matrix) {
        for (int[] row : matrix) {
            for (int value : row) {
                System.out.print(value + " ");
            }
            System.out.println();
        }
    }
}

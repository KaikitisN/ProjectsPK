package hw1;
/**
 * @author Neophytos kaikitis
 */
public class RichArray {
	private int[][] arr;

	/**
	 * The constructor with 1D table
	 * 
	 * @param arr
	 */
	public RichArray(int arr[]) {
		this.arr = new int[1][arr.length];
		for (int i = 0; i < arr.length; i++) {
			this.arr[0][i] = arr[i];
		}
	}

	/**
	 * The constructor with 2D table
	 * 
	 * @param arr
	 */
	public RichArray(int arr[][]) {
		this.arr = arr;
	}

	/**
	 * This method takes an array and reverse it if it is a 2D array it reverses
	 * each line
	 * 
	 * @return
	 */
	public RichArray reverse() {
		int[][] reverseArr = new int[arr.length][arr[0].length];
		for (int i = 0; i < arr.length; i++) {
			for (int j = 0; j < arr[0].length; j++) {
				reverseArr[i][j] = arr[i][arr[0].length - 1 - j];
			}
		}
		return new RichArray(reverseArr);
	}

	/**
	 * This method rotates the array to the right the first line becomes the last
	 * column and so on
	 * 
	 * @return
	 */
	public RichArray rotateRight() {
		int[][] rotateArr = new int[arr[0].length][arr.length];
		for (int i = 0; i < arr.length; i++) {
			for (int j = 0; j < arr[0].length; j++) {
				rotateArr[j][arr.length - 1 - i] = arr[i][j];
			}
		}
		return new RichArray(rotateArr);
	}

	/**
	 * This method rotates the array to the left the first line becomes the first
	 * column but in reverse and so on
	 * 
	 * @return
	 */
	public RichArray rotateLeft() {
		int[][] rotateArr = new int[arr[0].length][arr.length];
		for (int i = 0; i < arr.length; i++) {
			for (int j = 0; j < arr[0].length; j++) {
				rotateArr[arr[0].length - 1 - j][i] = arr[i][j];
			}
		}
		return new RichArray(rotateArr);
	}

	/**
	 * This method transposes the array turns the rows into columns and the columns
	 * into rows
	 * 
	 * @return
	 */
	public RichArray transpose() {
		int[][] trasposeArr = new int[arr[0].length][arr.length];
		for (int i = 0; i < arr.length; i++) {
			for (int j = 0; j < arr[0].length; j++) {
				trasposeArr[j][i] = arr[i][j];
			}
		}
		return new RichArray(trasposeArr);
	}

	/**
	 * This method ravels an array takes an array and turns it to an array with n
	 * columns
	 * 
	 * @param n the number of columns of the new array
	 * @return
	 */
	public RichArray ravel(int n) {
		int elem = arr.length * arr[0].length;
		int[][] ravelArr = new int[elem / n][n];
		int k = 0;
		for (int i = 0; i < elem / n; i++) {
			for (int j = 0; j < n; j++) {
				int rowIndex = k / arr[0].length;
				int colIndex = k % arr[0].length;
				ravelArr[i][j] = arr[rowIndex][colIndex];
				k++;
			}
		}
		return new RichArray(ravelArr);
	}

	/**
	 * This method unravels an array takes an array and puts it all in 1 line
	 * 
	 * @return
	 */
	public RichArray unravel() {
		int[] unravelArr = new int[arr.length * arr[0].length];
		int k = 0;
		for (int i = 0; i < arr.length; i++) {
			for (int j = 0; j < arr[0].length; j++) {
				unravelArr[k++] = arr[i][j];
			}
		}
		int[][] result = new int[1][arr.length * arr[0].length];
		result[0] = unravelArr;
		return new RichArray(unravelArr);
	}

	/**
	 * This method reshapes an array take an array and makes it an array of r rows
	 * and n columns
	 * 
	 * @param n the number of columns
	 * @return
	 */
	public RichArray reshape(int n) {

		if (((arr[0].length * arr.length) % n) == 0) {
			int r = (arr[0].length * arr.length) / n;
			int[][] reshapeArr = new int[r][n];
			int k = 0;
			for (int i = 0; i < r; i++) {
				for (int j = 0; j < n; j++) {
					reshapeArr[i][j] = arr[k / arr[0].length][k % arr[0].length];
					k++;
				}
			}
			return new RichArray(reshapeArr);
		} else {
			System.out.println("this tabel cannot be reshaped");
			return new RichArray(arr);
		}
	}

	/**
	 * This method joins 2 arrays if the two array have the same number of rows it
	 * takes the 2 arrays and links the one to the other
	 * 
	 * @param array the array to be joined
	 * @return
	 */
	public RichArray join(RichArray array) {
		if (arr.length == array.arr.length) {
			int c = arr[0].length + array.arr[0].length;
			int[][] joinArr = new int[arr.length][c];
			for (int i = 0; i < arr.length; i++) {
				for (int j = 0; j < c; j++) {
					if (j < arr[0].length) {
						joinArr[i][j] = arr[i][j];
					} else {
						joinArr[i][j] = array.arr[i][j - arr[0].length];
					}
				}
			}
			return new RichArray(joinArr);
		} else {
			System.out.println("this 2 RichArray cannot be joined because they don't have the same number of rows");
			return new RichArray(arr);
		}
	}

	/**
	 * This method stacks 2 arrays on top of each other if the arrays have the same
	 * 
	 * 
	 * @param array the array to be attached
	 * @throws thows an illegal argument exception if the number of columns the called array attaches it self under the other array 
	 * @return
	 */
	public RichArray stack(RichArray array) {
		if (arr[0].length == array.arr[0].length) {
			int r = arr.length + array.arr.length;
			int[][] stackArr = new int[r][arr[0].length];
			for (int i = 0; i < r; i++) {
				for (int j = 0; j < arr[0].length; j++) {
					if (i < arr.length) {
						stackArr[i][j] = arr[i][j];
					} else {
						stackArr[i][j] = array.arr[i - arr.length][j];
					}
				}
			}
			return new RichArray(stackArr);
		} else {
			throw new IllegalArgumentException("Cannot stack this 2 arrays ");
		}
	}

	/**
	 * This method return a slice (part) of the array
	 * 
	 * @param firstRow    the row that the first number is
	 * @param lastRow     the row that the last number is
	 * @param firstColumn the column that the first number is
	 * @param lastColumn  the column that the last number is
	 * @return
	 */
	public RichArray slice(int firstRow, int lastRow, int firstColumn, int lastColumn) {
		int[][] sliceArr = new int[lastRow - firstRow + 1][lastColumn - firstColumn + 1];
		for (int i = firstRow; i <= lastRow; i++) {
			for (int j = firstColumn; j <= lastColumn; j++) {
				sliceArr[i - firstRow][j - firstColumn] = arr[i][j];
			}
		}
		return new RichArray(sliceArr);
	}

	/**
	 * This method takes a part of the array and replaces it with another array if
	 * that array can fit in the array
	 * 
	 * @param array  the ray to be inserted
	 * @param row    which row to be inserted in
	 * @param column which column to be inserted in
	 * @return
	 */
	public RichArray replace(RichArray array, int row, int column) {
		// Check if the start position is within bounds
		if (row < 0 || row >= arr.length || column < 0 || column >= arr[0].length) {
			throw new IllegalArgumentException("Start position is out of bounds");
		}

		// Calculate the end position for replacement
		int endRow = row + array.arr.length;
		int endColumn = column + array.arr[0].length;

		// Check if the replacement fits into the original array
		if (endRow > arr.length || endColumn > arr[0].length) {
			throw new IllegalArgumentException("Replacement array does not fit into original array");
		}

		// Create a new array to store the replaced elements
		int[][] replacedArr = new int[arr.length][arr[0].length];

		// Copy elements from the original array and the replacement array
		for (int i = 0; i < arr.length; i++) {
			for (int j = 0; j < arr[0].length; j++) {
				if (i >= row && i < endRow && j >= column && j < endColumn) {
					replacedArr[i][j] = array.arr[i - row][j - column];
				} else {
					replacedArr[i][j] = arr[i][j];
				}
			}
		}

		// Return a new RichArray object initialized with the replaced array
		return new RichArray(replacedArr);
	}

	/**
	 * this method prints out the tables
	 */
	public String toString() {
		StringBuilder sb = new StringBuilder();
		for (int[] row : arr) {
			for (int value : row) {
				sb.append(value).append(" ");
			}
			sb.append("\n");
		}
		System.out.println("----------------------");
		return sb.toString();
	}
}

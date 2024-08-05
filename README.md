# FIRST-OCCURANCE-AND-LAST-OCCURANCE-OF-ELEMENT-IN-ARRAY

#include <iostream>
using namespace std;

int firstOccurrence(int arr[], int n, int key) {
    int start = 0;
    int end = n - 1;
    int mid;
    int ans = -1;

    while (start <= end) {
        mid = start + (end - start) / 2;

        if (arr[mid] == key) {
            cout << "The key is found at index " << mid << endl;
            ans = mid;
            end = mid - 1; // Continue searching on the left side for the first occurrence
        } else if (arr[mid] < key) {
            start = mid + 1;
        } else {
            end = mid - 1;
        }
    }

    return ans;
}

int lastOccurrence(int arr[], int n, int key) {
    int start = 0;
    int end = n - 1;
    int mid;
    int ans = -1;

    while (start <= end) {
        mid = start + (end - start) / 2;

        if (arr[mid] == key) {
            cout << "The key is found at index " << mid << endl;
            ans = mid;
            start = mid + 1; // Continue searching on the right side for the last occurrence
        } else if (arr[mid] < key) {
            start = mid + 1;
        } else {
            end = mid - 1;
        }
    }

    return ans;
}

int main() {
    int n;
    cout << "Enter the size of array: ";
    cin >> n;

    int arr[100];
    cout << "Enter the elements of array:" << endl;

    for (int i = 0; i < n; i++) {
        cout << "Element " << i + 1 << ": ";
        cin >> arr[i];
    }

    int key;
    cout << "Enter the element you want to search: ";
    cin >> key;

    int firstPosition = firstOccurrence(arr, n, key);
    int lastPosition = lastOccurrence(arr, n, key);

    if (firstPosition != -1) {
        cout << "First occurrence of " << key << " is at index " << firstPosition << endl;
    } else {
        cout << "Element " << key << " not found in the array." << endl;
    }

    if (lastPosition != -1) {
        cout << "Last occurrence of " << key << " is at index " << lastPosition << endl;
    } else {
        cout << "Element " << key << " not found in the array." << endl;
    }

    return 0;
}

#include<bits/stdc++.h>
#define size 7
using namespace std;

class Hashtable {
public:
    string h[size][2];

    Hashtable() {
        for (int i = 0; i < size; i++)
            for (int j = 0; j < 2; j++)
                h[i][j] = "---";
    }

    void insert(string key, string value) {
        int index = hashFunction(key);
        while (h[index][0] != "---")
            index = (index + 1) % size;
        h[index][0] = key;
        h[index][1] = value;
    }

    void display() {
        cout << "\n\t[Key]\t[Value]\n";
        for (int i = 0; i < size; i++) {
            for (int j = 0; j < 2; j++)
                cout << "\t" << h[i][j];
            cout << "\n";
        }
    }

    int hashFunction(string key) {
        int sum = 0;
        for (char c : key)
            sum += int(c);
        return sum % size;
    }

    void search(string key) {
        int index = hashFunction(key);
        while (h[index][0] != key && h[index][0] != "---")
            index = (index + 1) % size;
        if (h[index][0] == key)
            cout << "String '" << key << "' found at index " << index << "\n";
        else
            cout << "String '" << key << "' not found.\n";
    }

    void remove(string key) {
        int index = hashFunction(key);
        while (h[index][0] != key && h[index][0] != "---")
            index = (index + 1) % size;
        if (h[index][0] == key) {
            h[index][0] = "---";
            h[index][1] = "---";
            cout << "String '" << key << "' deleted from index " << index << "\n";
        } else {
            cout << "String '" << key << "' not found.\n";
        }
    }
};

int main() {
    int choice;
    Hashtable ht;
    do {
        cout << "\nEnter choice\n1. Insert  2. Display  3. Search  4. Remove\nChoice [1/2/3/4] ";
        cin >> choice;
        switch (choice) {
            case 1: {
                string key, value;
                cout << "Enter the key: ";
                cin >> key;
                cout << "Enter the value: ";
                cin >> value;
                ht.insert(key, value);
                break;
            }
            case 2:
                ht.display();
                break;
            case 3: {
                string key;
                cout << "Enter the string to search: ";
                cin >> key;
                ht.search(key);
                break;
            }
            case 4: {
                string key;
                cout << "Enter the string to delete: ";
                cin >> key;
                ht.remove(key);
                break;
            }
        }
    } while (choice < 5);
    return 0;
}

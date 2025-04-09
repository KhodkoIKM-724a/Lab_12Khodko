#include <iostream>
#include <vector>
#include <climits> // для INT_MAX та INT_MIN
using namespace std;

void знайтиСумуІДобутокІндексів(const vector<vector<int>>& матриця) {
    setlocale(LC_ALL, "");
    system("chcp 65001 > nul");

    int minVal = INT_MAX, maxVal = INT_MIN;
    int minRow = 0, minCol = 0, maxRow = 0, maxCol = 0;

    for (int i = 0; i < матриця.size(); ++i) {
        for (int j = 0; j < матриця[i].size(); ++j) {
            if (матриця[i][j] < minVal) {
                minVal = матриця[i][j];
                minRow = i;
                minCol = j;
            }
            if (матриця[i][j] > maxVal) {
                maxVal = матриця[i][j];
                maxRow = i;
                maxCol = j;
            }
        }
    }

    int сума = minRow + minCol + maxRow + maxCol;
    int добуток = (minRow * minCol) * (maxRow * maxCol);

    cout << "Мінімальний елемент: " << minVal << " на позиції [" << minRow << "][" << minCol << "]\n";
    cout << "Максимальний елемент: " << maxVal << " на позиції [" << maxRow << "][" << maxCol << "]\n";
    cout << "Сума індексів: " << сума << endl;
    cout << "Добуток індексів: " << добуток << endl;
}

int main() {
    vector<vector<int>> матриця = {
        {7, 2, 5},
        {4, 9, 1},
        {3, 6, 8}
    };

    знайтиСумуІДобутокІндексів(матриця);
    return 0;
}

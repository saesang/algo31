// 7576.cpp 토마토

#include <iostream>
#include <queue>
#include <algorithm>

#define X first
#define Y second
using namespace std;

int main()
{
    ios::sync_with_stdio(false);
    cin.tie(0);
    cout.tie(0);

    int board[1002][1002];
    int dist[1002][1002];
    int dx[4] = {1, 0, -1, 0};
    int dy[4] = {0, 1, 0, -1};
    int ans = 0;

    int n, m;
    cin >> m >> n;
    pair<int, int> xy;

    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            cin >> board[i][j];
        }
    }

    queue<pair<int, int>> q;

    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            if (board[i][j] == 1) // 1인부분 q삽입 -> bfs시작점이 여러개
            {
                q.push({i, j});
            }

            if (board[i][j] == 0)
            {
                dist[i][j] = -1;
            }
        }
    }

    while (!q.empty())
    {
        pair<int, int> cur = q.front();
        q.pop();

        for (int k = 0; k < 4; k++)
        {
            int nx = cur.X + dx[k];
            int ny = cur.Y + dy[k];

            if (nx < 0 || ny < 0 || nx >= n || ny >= m)
            {
                continue;
            }

            if (dist[nx][ny] > -1)
            {
                continue;
            }
            dist[nx][ny] = dist[cur.X][cur.Y] + 1;
            q.push({nx, ny});
        }
    }

    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            if (dist[i][j] == -1)          // 하나라도 -1이 생기면 모두 익지못함
            {
                cout << -1;
                return 0;
            }
            ans = max(ans, dist[i][j]);
        }
    }

    cout << ans;
}

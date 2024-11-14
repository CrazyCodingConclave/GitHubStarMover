import requests

# 配置信息
source_token = 'source_token'
source_username = 'source_username'
target_token = 'target_token'

# 请求头
source_headers = {
    'Authorization': f'token {source_token}',
    'Accept': 'application/vnd.github.v3+json'
}
target_headers = {
    'Authorization': f'token {target_token}',
    'Accept': 'application/vnd.github.v3+json'
}

def get_starred_repos(username, headers):
    """获取用户的Star列表"""
    url = f'https://api.github.com/users/{username}/starred'
    starred_repos = []
    while url:
        response = requests.get(url, headers=headers)
        if response.status_code == 200:
            starred_repos.extend(response.json())
            # 检查是否有更多页面
            link_header = response.headers.get('Link')
            if link_header:
                links = link_header.split(', ')
                for link in links:
                    if 'rel="next"' in link:
                        url = link[link.find('<')+1:link.find('>')]
                        break
                else:
                    url = None
            else:
                url = None
        else:
            print(f"Error fetching starred repos: {response.status_code}")
            url = None
    return starred_repos

def star_repo(repo_full_name, headers):
    """在目标账户上Star一个仓库"""
    url = f'https://api.github.com/user/starred/{repo_full_name}'
    response = requests.put(url, headers=headers)
    if response.status_code == 204:
        print(f'Successfully starred {repo_full_name}')
    else:
        print(f'Failed to star {repo_full_name}: {response.status_code}')

def main():
    # 获取源账户的Star列表
    print("Fetching starred repositories from source account...")
    starred_repos = get_starred_repos(source_username, source_headers)
    print(f"Found {len(starred_repos)} starred repositories.")

    # 在目标账户上Star相同的仓库
    print("Starring repositories on target account...")
    for repo in starred_repos:
        star_repo(repo['full_name'], target_headers)

if __name__ == "__main__":
    main()

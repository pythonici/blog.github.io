---
layout: post
title: You're up and running!
---

Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).

![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.
```
#include <iostream>
#include <map>
using namespace std; 
map<int, int> ans;
int main(int argc, char** argv) {
	ios::sync_with_stdio(false);
	int n, m;
	cin>> n>> m;	 
	for(int i = 0; i < n; i++){
		int num = 0, x; 
		for(int j = 0; j < m; j++) {
			cin>> x;
			num = (num<<1)+x;
		}
		ans[num]++;
	}
	int sum =0,maxn = (1<<m)-1, mid = maxn/2;
	for(map<int, int>::iterator it = ans.begin(); it != ans.end() ; it++){
		int x = it->first;
		if(mid < x) break;  
		int num = x^maxn;
		sum += ans[num]*it->second;
	}
	cout<< sum << '\n';
	return 0;
  ```

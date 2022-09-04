``` java
1.dp
// 状态 选择
//basecase
dp[0][0] = base;

for 状态1 in 状态1+选择 {
	for 状态2 in 状态2+选择 {
		dp[i][j] = 求最值(所有选择)；
	}
}


2.dfs 每个节点做选择, 暴力枚举，做好用的方法；
res[];
dfs(路径，选择列表) {
	if(路径 is target)
		res.add(路径);
		return;
	for(next in node.children){
		添加选择；
		dfs(next)
		撤销选择；
	}
}

3.bfs  —— 求最短路径    一层一层放入队列
Queue<Stirng> q = new LinkedList<String>();
Set<String> visited = new HashSet<String>();

q.offer(root);
visited.add(root);
int step = 0;

while(!q.size()){
	int sz = q.size();
	for(int i=0; i< sz;i++){
		TreeNode cur = q.poll();
	
		if(node is target)
			return step;
		
		for(node of cur.next) {
			if(!visited.contains(node)){
				q.offer();
			visited.add(node);
			}
		}
	}
	step++;

}
return step;


4.TreeNode
void traverse(TreeNode root) {
	//font
	traverse(root);
	//mid
	traverse(root);
	//back
}


5.slidewindow
	init Map  window & need 
	
	int left right = 0
	valid = 0 //有效位
	
	while(right < s.length())
	{
		char c  = s.charAt(right);
		right++;
		if(need.containsKey(c)){
			window[c]++;
			if(need[c] == window[c])
				valid++;
		}

		while(left need shrink){
			char d = s.charAt(left);
			left++;
			if(need.containsKey(c)){
				if(need[c] == window[c])
					valid--;
				window[c]--;
			}
		}

	}
	return len;

6.findMid
int binarySearch(int[] nums, int target) {
	int left = 0;
	int right = nums.length - 1; // 注意
	
	while(left <= right) {
		int mid = left + (right - left) / 2;
		
		if(nums[mid] == target)
			return mid;
		
		else if (nums[mid] < target)
			left = mid + 1; // 注意
		
		else if (nums[mid] > target)
			right = mid - 1; // 注意
	}
	return -1;
}

7.findLeftEdge
int binarySearch(int[] nums, int target) {
	int left = 0;
	int right = nums.length - 1; // 注意
	
	while(left <= right) {
		int mid = left + (right - left) / 2;
		
		if(nums[mid] == target)
			right = mid - 1;
		
		else if (nums[mid] < target)
			left = mid + 1; // 注意
		
		else if (nums[mid] > target)
			right = mid - 1; // 注意
	}
	Judge stack overflow and output
	return left;
}
8.findRightEdge
int binarySearch(int[] nums, int target) {
	int left = 0;
	int right = nums.length - 1; // 注意
	
	while(left <= right) {
		int mid = left + (right - left) / 2;
		
		if(nums[mid] == target)
			left = mid + 1;
		
		else if (nums[mid] < target)
			left = mid + 1; // 注意
		
		else if (nums[mid] > target)
			right = mid - 1; // 注意
	}
	Judge stack overflow and output
	return right;
}


```

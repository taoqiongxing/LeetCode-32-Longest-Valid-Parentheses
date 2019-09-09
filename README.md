# LeetCode-32 Longest Valid Parentheses
最长有效括号（刷爆难题6）

题目链接：https://leetcode-cn.com/problems/longest-valid-parentheses/submissions/

    class Solution:
    def longestValidParentheses(self, s: str) -> int:
        s=list(s)
        n=len(s)
        former=[]
        for i in range(1,n):
            if s[i]==')':
                j=i-1
                while j>0 and s[j]=='*':
                    j-=1
                if s[j]=='(':
                    s[i]='*'
                    s[j]='*'
        res=''.join(s).replace(')','(').split('(')
        ac=0
        for sub in res:
            ac=max(ac,len(sub))
        return ac
            

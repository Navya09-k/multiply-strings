class Solution:
    def multiply(self, num1: str, num2: str) -> str:
        res = [0] * (len(num1) + len(num2))
        for i, u in enumerate(reversed(num1)):
            for j, v in enumerate(reversed(num2)):
                res[i + j] += int(u) * int(v)
        for i in range(len(res) - 1):
            res[i + 1] += res[i] // 10
            res[i] %= 10 
        while len(res) > 1 and res[-1] == 0:
            res.pop()        
        return "".join(map(str, res[::-1]))     

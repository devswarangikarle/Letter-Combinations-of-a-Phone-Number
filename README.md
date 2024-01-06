# Letter-Combinations-of-a-Phone-Number
Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent. Return the answer in any order.  A mapping of digits to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.


class Solution:
    def letterCombinations(self, digits):
        def generate_combinations(index, current):
            if index == len(digits):
                result.append(current)
                return

            for char in digit_mapping[digits[index]]:
                generate_combinations(index + 1, current + char)

        if not digits:
            return []

        digit_mapping = {
            '2': 'abc',
            '3': 'def',
            '4': 'ghi',
            '5': 'jkl',
            '6': 'mno',
            '7': 'pqrs',
            '8': 'tuv',
            '9': 'wxyz'
        }

        result = []
        generate_combinations(0, '')
        return result


solution = Solution()
print(solution.letterCombinations("23")) 
print(solution.letterCombinations(""))    
print(solution.letterCombinations("2"))  

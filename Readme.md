# Two Sum (Solution)
    # Given an array of intergers nums and an interger target
    # Return indexes of two numbers such that they add up to target
    # You may assue that each input would have exactly one Solution
    # You may not use the same element twice
    # You can return the answer in any order

# Example 1
    #   Input: nums = [2,7,11,15], target = 9
    #   Output: [0,1]
    #   Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

# Example 2
    #   Input: nums = [3,2,4], target = 6
    #   Output: [1,2]

# Example 3:
    #   Input: nums = [3,3], target = 6
    #   Output: [0,1]

# Constraints:
    # 2 <= nums.length <= 104
    # -109 <= nums[i] <= 109
    # -109 <= target <= 109
    # Only one valid answer exists.

class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # Created a dictionary to remember the numbers and their location in the indexes
        num_indexes = {}
        # Repeats through the numbers along with the position in the indexes
        for i, num in enumerate(nums):
            # Calculate the complement needed to reach the target number
            # Complement - numbers, when added to the element, achieve a target sum
            complement = target - num
            # Check if the complement has been remembered
            if complement in num_indexes:
                # Spotted a pair that added up to the target number
                # Shares the position of the index
                return [num_indexes[complement], i]
            # If complment is not found, remember the current number and its index position
            num_indexes[num] = i

        # If no valid pair is found then return an empty list
        return []

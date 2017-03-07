import random


def choice_once():
    # r-type: (member, )
    return tuple(sorted(random.sample(range(1, 32), 6))), (random.randint(1, 16), )
    
def user_choice_random(num = 1):
    """
        r-type: (member, )
    """
    choice = []
    for i in range(num):
        choice.append(choice_once())
    return tuple(choice)
    
def add_digit(color):
    x = raw_input('1-%i>' %  color)
    if x.isdigit() and int(x) in range(1, color+1):
        return int(x)
    else:
        raise ValueError
    
def user_choice_manual():
    reds = set()
    while len(reds) < 6:
        reds.add(add_digit(33))
    bule = add_digit(16)
    
    return tuple(sorted(reds)), bule
    
def ret_choice():
    return choice_once()
    
def once_bouns(user_nums, ret_nums):
    right_reds = i = j = 0
    while i < 6 and j < 6:
        if user_nums[0][i] == ret_nums[0][j]:
            right_reds += 1
            i += 1
            j += 1
        elif user_nums[0][i] > ret_nums[0][j]:
            j += 1
        else:
            i += 1
    right_bules = int(user_nums[1][0] == ret_nums[1][0])
    if right_bules == 1 and right_reds == 6:
        return 10000000
    elif right_bules == 0 and right_reds == 6:
        return 3000000
    elif right_bules == 1 and right_reds == 5:
        return 3000
    elif right_bules == 1 and right_reds == 4:
        return 200
    elif right_bules == 0 and right_reds == 5:
        return 200
    elif right_bules == 1 and right_reds == 3:
        return 10
    elif right_bules == 0 and right_reds == 4:
        return 10
    elif right_bules == 1:
        return 10
    else:
        return 0
        
def test_100_years():
    pay_out = pay_in = 0
    for x in range(100 * 365):
        pay_out += 2
        user_nums = user_choice_random()[0]
        ret_nums = ret_choice()
        pay_in += once_bouns(user_nums, ret_nums)
    print("100 years late, you spend %i, and earn %i" % ( pay_out, pay_in))
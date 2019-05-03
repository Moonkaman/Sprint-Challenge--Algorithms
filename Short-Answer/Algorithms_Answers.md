Exercise I
a)  a=0 O(1)
    while (a < n * n * n): O(3n)
      a=a + n * n O(1)

I think that the above code is O(3n) which simplifies down to O(n) because you drop the
leading constants.

b)  sum=0
    for i in range(n): O(n)
      i += 1
      for j in range(i + 1, n): O(n)
        j += 1
        for k in range(j + 1, n): O(n)
          k += 1
          for l in range(k + 1, 10 + k): O(9) which reduces to O(1)
            l += 1
            sum += 1

I think that the above code is O(n ^ 3) because of the 3 nested for loops but the last
one is constant because it's always doing the same number of operations

c) def bunnyEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)

I think that the above code is O(n) because it is called n times, it might be O(n-1)
but again the constants are dropped so thats why I think it's O(n)

Exercise II
I would probably do it the binary search way so the first thing to do would be to divide the total
floors by 2 and go to that floor, then I would drop an egg, if it broke I would divide the bottom
floors by two again and repeat until I found f.

in psuedo code that would look something like this

def find_f(total_floors):
  if len(total_floors) == 1:
    return total_floors[0]
  else:
    floor_to_try = len(total_floors) / 2
    go_to_floor(total_floors[floor_to_try])
    if drop_egg() == 'break':
      find_f(total_floors[:go_to_floor])
    else:
      find_f(total_floors[go_to_floor:])

It would look something like that, I'm not sure if there's some small thing I missed but that should
be close at least, as for the time complexity this is a binary search which I think is O(log(n))
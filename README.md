# Student-Trekking-Groups-and-Pairing-Challenge---Python-Solution

A school has organized a field trip for a class of N students, of which X students are boys, and the remaining students are girls.
Everyone is excited to go trekking, and must form groups of size exactly K to do so. However, boys will only form groups among themselves, and girls will only form groups among themselves.
Both boys and girls will form as many groups as possible.
The remaining students can either dance around a bonfire, or just read books.
Dancing around the bonfire requires a pair of one girl and one boy, while reading is done alone.
Reading is much more boring than dancing, so students will try to avoid it. What's the minimum number of students who will be engaged in reading?

def min_students_reading():
    T = int(input())  
    results = []
    
    for _ in range(T):
        N, X, K = map(int, input().split())  
        boys = X
        girls = N - X
        
        rem_boys = boys % K
        rem_girls = girls % K
        
        pairs = min(rem_boys, rem_girls)
        
        remaining_reading = (rem_boys - pairs) + (rem_girls - pairs)
        
        results.append(remaining_reading)
    
    for result in results:
        print(result)

min_students_reading()

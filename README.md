# Exam Timetables using MOGA
An attempt in solving exam scheduling with Multi-Objective Genetic Algorithm  

## Dataset
University of Toronto Benchmark Data v2  
### Input:  
`*.res` or `n::int` from `stdin` - number of time slots  
`*.crs` - exam id, number os students enrolled  
`*.stu` - $k$-th line has a list of exams of the $k$-th student  

### Output:
`*.sol` - exam id, time slot

## Encoding
Vector `v[exam_id] := time_slot`

## Constraints
### Hard
- student can't be present at 2 or more exams simultaneously
- no more than $R$ (rooms available) exams can occur at the same time
### Soft
- minimize the number of exams per student per day
- maximise the gap between exams for each student

## Fitness function
I will try two approaches:  
1. Just a linear combination of fitness values on each constraint
2. Multi-objective approach using [Pareto order](https://en.wikipedia.org/wiki/Pareto_efficiency#Pareto_order)

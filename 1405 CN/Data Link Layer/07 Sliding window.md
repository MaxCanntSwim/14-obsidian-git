sending multiple frames back to back, with frame numbers, acks include frame number. ![[Screenshot 2023-04-25 at 12.07.11.jpg]]

# State of frames
![[Screenshot 2023-04-25 at 12.07.46.jpg]]

![[Screenshot 2023-04-25 at 12.08.33.jpg]]
Question: How to choose k such that there are no periods in which bandwidth is not used? 
Multiple things to keep in mind: 
- size of the buffer, we don't want to have overflow
- we don't want to have overlap on the bar ![[Screenshot 2023-04-25 at 12.12.32.jpg]]

## Alternative Go-back-N
![[Screenshot 2023-04-25 at 12.17.16.jpg]]
## Alternative figure Selective repeat
![[Screenshot 2023-04-25 at 12.17.45.jpg]]
We acknowledge only five and inexplicit 2, 3 and 4 as well. 

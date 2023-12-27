**EC2 Reserved Instances**
- Recommended for steady-state usage application
- Reservation Period: 1 to 3 Years
- Pay as you use (No upfront)
- Buy/Sell instances in Marketplace

**Convertible Reserved Instance**
- Can change the instance type
- Lower discount
- Cannot sell unused instances on the Reserved Instance Marketplace

**EC2 Savings Plan**
- Discount based on usage terms
- Usage beyong savings plan is billed at On-demand price
- Locked to a instance family and Region. But can change instance settings

**EC2 Spot Instances**
- Work on a bidding basis where you are willing to pay a specific max hourly rate for the instance.
- Your instance can terminate if the spot price increases (your MAX price < current spot price).
- Spot blocks are designed not to be interrupted
- Good for workloads that are resilient to failure
- **NOT for critical jobs**

**EC2 Dedicated Host**
- A physical server with EC2 dedicated to you
- Server hardware is allocated to a specific company (not shared with other companies)
-  Most Expensive
-  Pay per Host
-  Reservation: 1 to 3 years
-  Useful for software that have BYOL (Bring Your Own License) or for companies that have strong regulatory or compliance needs

**EC2 Dedicated Instances**
- Dedicated hardware
- Billed per instance
- No control over instance placement (Hardware can move after Start/Stop)

> ### Difference between Dedicated Host & Dedicated Instances 
> - Dedicated Instance does not work like this. Your instance runs on some dedicated hardware. Its not lockdown to you. If you stop/start instance, you can get some other hardware somewhere else. Basically, the hardware is "yours" (you are not sharing it with others) for the time your instance is running. You stop/start it, you may get different physical machine later on (maybe older, maybe newer, maybe its specs will be a bit different), and so on. So your instance is moved around on different physical servers - whichever is not occupied by others at the time.  
> - With Dedicated Host the physical server is basically yours. It does not change, it's always the same physical machine for as long as you are paying.

**EC2 Capacity Reservations**
- Ensure you have the available capacity in an AZ to launch EC2 instances when needed
- No time commitment, No billing discount
- Charged at On-Demand rate whether you run instance or not
- Good for short term, uninterrupted workloads in specific AZ

## EC2 Spot Instance 
- **One-time:** Request once opened, spins up the spot instances and the request closes.
- **Persistent:**
  - Request will stay disabled while the spot instances are up and running.
  - It becomes active after the spot instance is interrupted.
  - If you stop the spot instance, the request will become active only after you start the spot instance.
- You can only cancel spot instance requests that are open, active, or disabled.
- Cancelling a Spot Request does not terminate instances. You must first cancel a Spot Request, and then terminate the associated Spot Instances.

## EC2 Spot Fleets
- Combination of spot and on-demand instances (optional) that tries to optimize for cost or capacity
- Launch Templates must be used to have on-demand instances in the fleet
- Strategies to allocate Spot Instances:
  - lowestPrice - from the pool with the lowest price (cost optimization, short workload)
  - diversified - distributed across all pools (great for availability, long workloads)
  - capacityOptimized - pool with the optimal capacity for the number of instances

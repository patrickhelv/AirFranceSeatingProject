# AirFranceSeatingProject
Project in collaboration with AirFrance to optimize seating in a plane.
Our dataset consists of multiple Excel files, each containing different types of passengers, including **first-class** and **economy-class** travelers, **wheelchair users**, and **stretcher** passengers.

We aim to develop an optimization model to allocate seating while adhering to the following criteria:

1. Group Seating
- Members of the same group should be seated next to each other in the same row and on the same aisle.
- The highest priority within a group is given to children, meaning a child must always sit with at least one parent.
- If necessary, groups may be split to ensure a child is seated next to a parent, taking priority over other group constraints.

2. Transit Passengers
- Passengers with connecting flights should be seated at the front of the plane to facilitate a quicker transfer.
- However, this constraint is of lower priority compared to seating class and child-parent grouping.
- If business class seats in the front are fully occupied, transit passengers may be assigned other available front-row seats.

3. Seating Class
Passengers must be seated according to their ticket class:
- First-class passengers should be seated in first-class sections at the front.
- Economy-class passengers must be seated behind the business-class section.

4. Wheelchair Users
A wheelchair user occupies four seats:
- Two seats in their assigned row.
- The two seats directly in front of them.

As a result, we must remove:
- The seat next to the wheelchair user.
- The two seats in the row directly in front.
Additionally, **grouping** and **child-parent constraints** still apply to wheelchair users.

5. Stretcher Passengers
A stretcher passenger occupies three full rows.
- The passenger is positioned in the middle seat of their row.
- The entire row in front and behind must remain empty.
- All three seats in each of these rows are blocked to accommodate the stretcher.

6. Weight Distribution (Barycentre Constraint)
Passenger weight must be evenly distributed across the aircraft to maintain balance.
The model must take into account the weight differences among adults, children, wheelchair users, and stretcher passengers.

## Dependencies
- `Gurobi` (https://a-farahat-15071.readthedocs.io/en/latest/installing_gurobi.html)
- `jupyter notebook`
- `numpy`
- `pandas`
- `matplotlib`

## How to run 
Go to the `notebook_seating_project_Air_France.ipnyb` notebook.



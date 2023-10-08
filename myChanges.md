# Changes
Added function to a_star_grid_2d class(found at core\math\a_star_grid_2d.h) for findinng available cells in range(i.e, g_cost from start point to end point is known, so find all points that cost strictly less than or less than equal to g_cost to travell to).

# How to

1. Clone the repo

2. Navigate to the repo location.

3. Compile/Build for your platform using ```scons -j<threads to use> platform=<platform> dev_build=yes```

4. Test the changes using the snippet below:
```
    var astar_grid = AStarGrid2D.new()
	astar_grid.diagonal_mode = AStarGrid2D.DIAGONAL_MODE_NEVER
	astar_grid.default_compute_heuristic = AStarGrid2D.HEURISTIC_MANHATTAN
	astar_grid.default_estimate_heuristic = AStarGrid2D.HEURISTIC_MANHATTAN
	astar_grid.region = Rect2i(0, 0, 32, 32)
	astar_grid.cell_size = Vector2(16, 16)
	astar_grid.update()
	# astar_grid.set_point_solid(Vector2i(1,0),true)
	# astar_grid.set_point_solid(Vector2i(2,1),true)
	print(astar_grid.get_id_path(Vector2i(0, 0), Vector2i(2, 2)))
	print(astar_grid.get_id_path_range(Vector2i(2,2),2,AStarGrid2D.LESSOREQUAL))
```

5. If everything went smoothly you should see a console output similar to this: 

```[(2, 2), (3, 2), (4, 2), (3, 3), (1, 2), (1, 3), (0, 2), (2, 3), (2, 4), (1, 1), (2, 1), (2, 0), (3, 1)]```

# To Do

Option for ignoring the cell that called the function (units can't target themselves,right? (≧︿≦))

Add custom sorter to sort points

and many more.
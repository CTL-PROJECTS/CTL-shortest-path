import numpy as np

        def load_configuration(filename):
            # loads a polymer configuration with n steps (n+1 nodes) and obstacle coordinates from filename
            # configuration file format: 
            # molecule-number x y 
            # molecule-number x y 
            # ...
            #
            # returns n, n+1 coordinates of the monomers (x_polymer), obstacles, and obstacle coordinates (x_obstacle)
            print("loading 2D configuration from "+filename+" ..")
            data = np.genfromtxt(filename, dtype=float)
            n = -1
            obstacles = 0
            x_polymer = np.empty((0,2),dtype=float)
            x_obstacle = np.empty((0,2),dtype=float)
            for j in range(nodes):
                mol = int(data[j,0])
                if mol==1:
                    n += 1
                    x_polymer = np.append(x_polymer,[[data[j,1],data[j,2]]],axis=0)
                else:
                    obstacles += 1
                    x_obstacle = np.append(x_obstacle,[[data[j,1],data[j,2]]],axis=0)
            print("returned: 1 polymer with n+1 = "+str(n+1)+" nodes (numpy array x_polymer[:,:]) and "+str(obstacles)+" obstacles (x_obstacle[:,:])")
            return n,x_polymer,obstacles,x_obstacle

The EVUF format uses the following header:

| ***size*** | **4B**             | **4B**        | **4B**         | **4B**               | **4B**                | **2B**                |
|------------|--------------------|---------------|----------------|----------------------|-----------------------|-----------------------|
| ***data*** | **"EVUF" (magic)** | **width (w)** | **height (h)** | **chunk width (cw)** | **chunk height (ch)** | **packet depth (pd)** |

nw = floor(log2(w/cw)/4)*4  
nh = floor(log2(h/ch)/4)*4

the body is composed of chunks:

| ***size*** | **(nw)b**     | **(nh)b**     | **(pd\*nw\*nh)B** |
|------------|---------------|---------------|-------------------|
| ***data*** | **x pos (x)** | **y pos (y)** | **content (c)**   |

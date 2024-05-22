# Graphviz

# Prep
Install graphviz, including dot

# Build
```bash
for GVFILENAME in $(ls -1 *.gv | cut -d. -f1 ); do dot -Tpng ${GVFILENAME}.gv -o ../img/${GVFILENAME}.png;done
```

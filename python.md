for PS1 POUT         | 320.000    | Watts      | ok    | na        | na        | na        | 1200.000  | 1240.000  | 1264.000  
```
with open(file_path) as f:
  for line in f:
    try:
      ps1_pout = float(line.split("|")[1].strip())
    except:
      ps1_pout = None
```

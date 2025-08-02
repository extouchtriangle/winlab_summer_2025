---
title: Weekly Reports
layout: home
---

# Summer Internship: Weekly Progress Reports

## Week 1

- Used hacky way to decrease framerate of file:

  ```py
  os.system(f"vrs copy 30fps.vrs --to frame{i}.vrs --around {current_time} 0.02 > /dev/null")
  ```

  By adjusting the time range so that exactly one frame would go into the output
  file, a selected subset of the frames could then be merged into a file that
  had a lower framerate.

---
title: Weekly Reports
layout: home
---

# Summer Internship: Weekly Progress Reports

## Week 1

- Used hacky way to decrease framerate of file:

  ```python
  os.system(f"vrs copy 30fps.vrs --to frame{i}.vrs --around {current_time} 0.02 > /dev/null")
  ```

  By adjusting the time range so that exactly one frame would go into the output
  file, a selected subset of the frames could then be merged into a file that
  had a lower framerate.

- Then, MPS flagged the file as having half of the frames dropped, because
  of a metadata tag in the file telling it that half of the frames were dropped.
- I ended up modifying some sample code in the repo to change the metadata tag
  using the `->set()` API:

```cpp
 void doDataLayoutEdits(const CurrentRecord& record, size_t blockIndex, DataLayout& dl) override {
    if (record.recordType == Record::Type::CONFIGURATION) {
      const auto& newSpec = getExpectedLayout<ImageSpec>(dl, blockIndex);
      dl.findDataPieceValue<double>("nominal_rate")->print(std::cout, "");
      // cout << "Patching value" << "\n";
      // double x = 15;
      double rate;
      cin >> rate;
      dl.findDataPieceValue<double>("nominal_rate")->set(rate);
      // cout << "Patching value complete" << "\n";
      dl.findDataPieceValue<double>("nominal_rate")->print(std::cout, "");
    }
  }
```

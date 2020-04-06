# One Shot Learning for 2D Shapes

Please check out Demo.ipynb

By translating images into timeseries, we show that it is possible to classify 2D shapes in a scale, rotation, and translation invariant manner while only having seen a single example of each class.

Requires khiva, see installation instructions from https://github.com/shapelets/khiva-python

The basics of the approach is outlined as follows:
1. Beginning with an image, the center of the shape is found by using a minimal encompassing circle.
2. From that center point, we scan outwards at different angles until we reach the sides of shape. That distance is the value associated with the angle
3. Each angle represents a timestep and so a timeseries is created from the shape.
4. At test time, a timeseries is generated from the test image and then compared to training timeseries.
5. SBD distance is used to compare the shape of the timeseries irrespective of where the periods start and the scale of the timeseries.

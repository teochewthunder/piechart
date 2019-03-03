# Pie Chart

The background is a circular div, with the *overflow* property set to *hidden*.

## Data
- A JSON object is used to hold the data.
- Functions are provided for calculating totals.
- The *(data value / total) x 100* is the *percentage*.
- This is applied to *percentage / 100 => (x / 360)*. Because the entire pie is 360 degrees, and we need to figure out how much of the pie each data value is going to take up.

## CSS Representation
- The circle is further divided into two vertical rectangular halves - left and right.
- Representation begns at 0 degrees. All rendering begins on the right half.
- Data is arranged from largest to smallest.
  - Each data value is divided into 90 degree quadrants. A full 45 degree data piece will be a square div. If it is more than 90 degrees, then we first render a 90 degree value before adding a second one, then rotating it counter-clockwise so that the result looks like one big rendered slice.
  - Repeat for values greater than 180 degrees, 270 degrees, etc.
 - For any piece that exceeds the 180 degree mark, the piece will be re-rendered in the left half.

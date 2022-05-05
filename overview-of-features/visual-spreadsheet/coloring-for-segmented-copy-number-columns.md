# Coloring for Segmented Copy Number Columns

When there are no overlapping segments, Xena displays the value and color of the copy number segment as indicated in the column legend at the bottom of the column.

When there are overlapping segments, Xena follows these steps:

1. Compute overlaps by slicing segments that overlap with other segments. For example if there was a segment from chr1:10000-20000 and a segment from chr1:10050-10100, then resulting segments from this step would be chr1:10000-10050, chr1:10050-10100, and chr1:10100-20000.
2. For each segment defined in step 1, determine which segments in the original data overlap with this segment.
3. Divide data segments into those that are greater than copy number neutral (i.e. are amplifications) and those that are less than copy number neutral (i.e. are deletions). Average the segments for each of these two groups
4. Take the average of the amplifications and the average of the deletions and determine their colors based on the color legend. Then pick a color that is in between the two colors and color the segment that color. An example would be that if the amplifications are red and deletions are blue, the resulting color from a strong amplification and a strong deletion would be purple. Note that copy number neutral in this example would be white.

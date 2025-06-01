
# Load VennDiagram package
install.packages("VennDiagram", dependencies=TRUE)  # Install if not already installed
library(VennDiagram)


# Move to a new plotting page
grid.newpage()


# Define datasets
df1 <- GSE26910
df2 <- GSE29431
df3 <- GSE3744
df4 <- GSE42568


# Get dataset sizes
df1_size <- nrow(df1)  
df2_size <- nrow(df2)  
df3_size <- nrow(df3)  
df4_size <- nrow(df4)  


# Compute intersection sizes
cross_12 <- length(intersect(df1$Genes1, df2$Genes2))
cross_13 <- length(intersect(df1$Genes1, df3$Genes3))
cross_14 <- length(intersect(df1$Genes1, df4$Genes4))
cross_23 <- length(intersect(df2$Genes2, df3$Genes3))
cross_24 <- length(intersect(df2$Genes2, df4$Genes4))
cross_34 <- length(intersect(df3$Genes3, df4$Genes4))

cross_123 <- length(Reduce(intersect, list(df1$Genes1, df2$Genes2, df3$Genes3)))
cross_124 <- length(Reduce(intersect, list(df1$Genes1, df2$Genes2, df4$Genes4)))
cross_134 <- length(Reduce(intersect, list(df1$Genes1, df3$Genes3, df4$Genes4)))
cross_234 <- length(Reduce(intersect, list(df2$Genes2, df3$Genes3, df4$Genes4)))

cross_1234 <- length(Reduce(intersect, list(df1$Genes1, df2$Genes2, df3$Genes3, df4$Genes4)))



# Save as PNG
#png("venn_diagram.png", width = 1200, height = 1200, res = 300)
draw.quad.venn(
  area1 = df1_size,
  area2 = df2_size,
  area3 = df3_size,
  area4 = df4_size,
  n12 = cross_12,
  n13 = cross_13,
  n14 = cross_14,
  n23 = cross_23,
  n24 = cross_24,
  n34 = cross_34,
  n123 = cross_123,
  n124 = cross_124,
  n134 = cross_134,
  n234 = cross_234,
  n1234 = cross_1234,
  category = c("GSE26910", "GSE29431", "GSE3744", "GSE42568"),
  fill = c("Red", "Yellow", "Blue", "Green")
)

getwd()
grid.newpage()  # Open a new page


# Save as PDF
pdf("venn_diagram.pdf", width = 8, height = 8)
draw.quad.venn(
  area1 = df1_size,
  area2 = df2_size,
  area3 = df3_size,
  area4 = df4_size,
  n12 = cross_12,
  n13 = cross_13,
  n14 = cross_14,
  n23 = cross_23,
  n24 = cross_24,
  n34 = cross_34,
  n123 = cross_123,
  n124 = cross_124,
  n134 = cross_134,
  n234 = cross_234,
  n1234 = cross_1234,
  category = c("GSE26910", "GSE29431", "GSE3744", "GSE42568"),
  fill = c("Red", "Yellow", "Blue", "Green")
)
dev.off()  # Close PDF file



# Save as TIFF
tiff("venn_diagram.tiff", width = 1200, height = 1200, res = 300)
draw.quad.venn(
  area1 = df1_size,
  area2 = df2_size,
  area3 = df3_size,
  area4 = df4_size,
  n12 = cross_12,
  n13 = cross_13,
  n14 = cross_14,
  n23 = cross_23,
  n24 = cross_24,
  n34 = cross_34,
  n123 = cross_123,
  n124 = cross_124,
  n134 = cross_134,
  n234 = cross_234,
  n1234 = cross_1234,
  category = c("GSE26910", "GSE29431", "GSE3744", "GSE42568"),
  fill = c("Red", "Yellow", "Blue", "Green")
)
dev.off()  # Close TIFF file



# Save as JPEG
jpeg("venn_diagram.jpg", width = 1200, height = 1200, res = 300)
draw.quad.venn(
  area1 = df1_size,
  area2 = df2_size,
  area3 = df3_size,
  area4 = df4_size,
  n12 = cross_12,
  n13 = cross_13,
  n14 = cross_14,
  n23 = cross_23,
  n24 = cross_24,
  n34 = cross_34,
  n123 = cross_123,
  n124 = cross_124,
  n134 = cross_134,
  n234 = cross_234,
  n1234 = cross_1234,
  category = c("GSE26910", "GSE29431", "GSE3744", "GSE42568"),
  fill = c("Red", "Yellow", "Blue", "Green")
)
dev.off()  # Close JPEG file



# Display the working directory
getwd()  # Check where the files are saved


# Display the Venn diagram in R plotting window
grid.newpage()  # Open a new page
draw.quad.venn(
  area1 = df1_size,
  area2 = df2_size,
  area3 = df3_size,
  area4 = df4_size,
  n12 = cross_12,
  n13 = cross_13,
  n14 = cross_14,
  n23 = cross_23,
  n24 = cross_24,
  n34 = cross_34,
  n123 = cross_123,
  n124 = cross_124,
  n134 = cross_134,
  n234 = cross_234,
  n1234 = cross_1234,
  category = c("GSE26910", "GSE29431", "GSE3744", "GSE42568"),
  fill = c("Red", "Yellow", "Blue", "Green")
)

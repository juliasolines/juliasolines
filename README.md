function setup() {
  createCanvas(600, 800);
  noStroke();
}

function draw() {
  background("white");

  let h = hour() % 24;
  let m = minute() % 60 ;
  let s = second() % 60 ;


stroke ("blue");
  drawGrid(100, 60, 3, 8, h, 40, 45, "rgb(146,146,241)"); // Hours
  drawGrid(250, 60, 10, 6, m, 27, 32, "lightblue"); // Minutes
  drawGrid(250, 260, 10, 6, s, 17, 22, "rgb(214,227,231)"); // Seconds

}

function drawGrid(x, y, cols, rows, filledCount, size, spacing, color) {
  let count = 0;
  let r = 0;
  
  while (r < rows) {
    let c = 0; 
    while (c < cols) {
      let cy = y + r * spacing;
      let cx = x + c * spacing;

      if (count < filledCount) {
        fill(color); 
      } else {
        noFill(); 
      }

      ellipse(cx, cy, size, size);
      count++;
      c++;
      // console.log("c: ", c);
    }
    r++;
    // console.log("r: ", r);
  }
}

//Global Variables
float drawingSurfaceX, drawingSurfaceY, drawingSurfaceWidth, drawingSurfaceHeight, drawingDiameter;
//float tempX, tempY, tempWidth, tempHeight;
//float rectX, rectY, rectWidth, rectHeight;
float stampX, stampY, stampWidth, stampHeight;
float stampRX, stampRY, stampRWidth, stampRHeight;
float thinX, thinY, thinWidth, thinHeight;
float thickX, thickY, thickWidth, thickHeight;
float clearButtonX, clearButtonY, clearButtonWidth, clearButtonHeight;
float backX, backY, backWidth, backHeight;
float backX1, backY1, backWidth1, backHeight1;
float backX2, backY2, backWidth2, backHeight2;
float eraseX, eraseY, eraseWidth, eraseHeight;
float quitButtonX, quitButtonY, quitButtonWidth, quitButtonHeight;
float lineToolX, lineToolY, lineToolWidth, lineToolHeight;
color redC=#E2252B;
color greenC=#1fd655;
color blueC=#0066FF;
color yellow=#FFFF00;
color orange=#FD6A02;
color violet=#8A2BE2;
color blueGreen=#40E0D0;
color yellowGreen=#BFFF00;
color pinkC=#F8C8DC;
color yellowOrange=#FA9336;
color white=#FFFFFF;
color black=#000000;
float masterStroke= 1;
color resetWhite=#FFFFFF;
color blue=#FFB7B2, pink=#F8C8DC, resetButtonColour=#C3B1E1, grey=#CCCCC4, flower=#FDFD96, bell=#c6e2e9, buttonFill;
boolean draw=false, lineTool=true, stamp=false, stampR=false, erase=false, thin=false, thick=false, back=false, back1=false, back2=false;
//boolean tempON=false, rect=false;
//
String quitButtonText= "X";
String lineToolText= "Pen";
String stampText= "Circle Stamp";
String clearButtonText = "Clear";
String stampRText = "Square Stamp";
String eraseText= "Eraser";
String thinText= "Thin";
String thickText= "Thick";
//String tempText= "Box Colorpage";
PFont buttonFont;
color purple = #2C08FF; //Note Night Mode Friendly, all of the blue is included
//
void setup()
{
  //Display Geometry
  size(500, 600); //Portraint
  background(white);
  println (width, height, displayWidth, displayHeight);
  int appWidth = width;
  int appHeight = height;
  if ( width > displayWidth || height > displayHeight ) { //CANVAS in Display Checker
    //CANVAS Too Big
    appWidth = displayWidth;
    appHeight = displayHeight;
    println("CANVAS needed to be readjusted to fit on your monitor.");
  } else {
    println("CANVAS is Good to go on your display.");
  }//End CANVAS in Display Checker
  //Display Orientation
  String ls="Landscape or Square", p="portraint", DO="Display Orientation:", instruct="Please turn your phone";
  String orientation = ( appWidth>=appHeight ) ? ls : p; //Ternary Operator, repeats the IF-Else structure to populate a variable
  println( DO, orientation );
  if ( orientation==p ) { //Test for chosen display orientation
    println("Good to Go");
  }
    println(instruct);
  //
  //Population
  int centerX = width*1/2;
  int centerY = height*1/15;
  float centeringButtonWidth = width*8.5/20;
  int centeringButtonHeight = height*1/15;
  lineToolX = width*16.5/20;
  lineToolY = centerY + centeringButtonHeight*1/10;
  lineToolWidth = width*1/6;
  lineToolHeight = height*1/15;
  stampX = width*16.5/20;
  stampY = height*1/6.5;
  stampWidth = width*1/6;
  stampHeight = height*1/15;
  eraseX = width*16.5/20;
  eraseY = height*1/2.1;
  eraseWidth = width*1/6;
  eraseHeight = height*1/15;
  thinX = width*16.5/20;
  thinY = height*1/1.8;
  thinWidth = width*1/13;
  thinHeight = height*1/16;
  thickX = width*18.5/20;
  thickY = height*1/1.8;
  thickWidth = width*1/13;
  thickHeight = height*1/16;
  //tempX = width*16.5/20;
  //tempY = height*1/1.3;
  //tempWidth = width*1/15;
  //tempHeight = height*1/16;
  //rectX = centerX;
  //rectY = centerY;
  //rectWidth = centerX;
  //rectHeight = centerY;
  stampRX = width*16.5/20;
  stampRY = height*1/4.3;
  stampRWidth = width*1/6;
  stampRHeight = height*1/15;
  clearButtonX = width*16.5/20;
  clearButtonY = height*1/3.2;
  clearButtonWidth = width*1/6;
  clearButtonHeight = height*1/15;
  backX = width*15.7/20;
  backY = height*1/2.5;
  backWidth = width*1/17;
  backHeight = height*1/18;
  backX1 = width*17.3/20;
  backY1 = height*1/2.5;
  backWidth1 = width*1/17;
  backHeight1 = height*1/18;
  backX2 = width*18.7/20;
  backY2 = height*1/2.5;
  backWidth2 = width*1/17;
  backHeight2 = height*1/18;
  quitButtonX = centerX + centeringButtonWidth;
  quitButtonY = centerY - centeringButtonHeight;
  quitButtonWidth = width*1/15;
  quitButtonHeight = height*1/15;
  drawingSurfaceX = width*0;
  drawingSurfaceY = height*0;
  drawingSurfaceWidth = 500;
  drawingSurfaceHeight = 600;
  drawingDiameter = width*1/100;
  //
  //Text Setup
  //String[] fontList = PFont.list(); //To list all fonts available on system
  println("Start of Console");
  //printArray(fontList); //For listing all possible fonts to choose, then createFont
  buttonFont = createFont ("times new roman", 30); //Must also Tools / Create Font / Find Font / Do Not Press "OK"
  //
}//End setup
//
void draw() {
  //
  //rect ( tempX, tempY, tempWidth, tempHeight );
  //rect ( rectX, rectY, rectWidth, rectHeight );
  //
  strokeWeight(1);
  fill(redC );
  rect(10, 10, 25, 25 );
  fill(blueC );
  rect(35, 10, 25, 25 );
  fill(greenC);
  rect(10, 35, 25, 25);
  fill(yellow);
  rect(35, 35, 25, 25);
  fill(orange);
  rect(10, 60, 25, 25);
  fill(violet);
  rect(35, 60, 25, 25);
  fill(blueGreen);
  rect(10, 85, 25, 25);
  fill(yellowGreen);
  rect(35, 85, 25, 25);
  fill(pink);
  rect(10, 110, 25, 25);
  fill(yellowOrange);
  rect(35, 110, 25, 25);
  fill(white);
  rect(10, 135, 25, 25);
  fill(black);
  rect(35, 135, 25, 25);
  //
  if(mousePressed) {
   if(mouseX > 10 && mouseX < 35) {
      if(mouseY >10 && mouseY < 35){
        stroke(redC);
      }
      if(mouseY>35 && mouseY < 60){
        stroke(greenC);
      }
      if(mouseY>60 && mouseY<85){
        stroke(orange);
      }
      if(mouseY>85 && mouseY<110){
        stroke(blueGreen);
      }
      if(mouseY>110 && mouseY<135){
        stroke(pinkC);
      }
      if(mouseY>135 && mouseY<160){
        stroke(white);
      }
    }
    if(mouseX > 35 && mouseX < 60){
      if( mouseY > 10 && mouseY <35){
        stroke(blueC);
      }
      if(mouseY > 35 && mouseY < 50){
        stroke(yellow);
      }
      if(mouseY > 60 && mouseY < 85){
        stroke(violet);
      }
      if(mouseY >85 && mouseY < 110) {
        stroke(yellowGreen);
      }
      if(mouseY > 110 && mouseY <135){
        stroke(yellowOrange);
      }
      if(mouseY >135 && mouseY <160){
        stroke(black);
      }
    }
 }
 //
  if ( erase == true ) {
    stroke(white);
   }
  //
  if ( back == true) {
        if ( erase == true ) {
            stroke(flower);
   }
  }
  //
    if ( back1 == true) {
        if ( erase == true ) {
        stroke(white);
   }
  }
  //
    if ( back2 == true) {
        if ( erase == true ) {
        stroke(bell);
   }
  }
  //
 //
  //if ( mouseX>tempX && mouseX<tempX+tempWidth && mouseY>tempY && mouseY<tempY+tempHeight ) tempON=true;
  //
  //fill(white);
  //if ( tempON==true ) rect( rectX, rectY, rectWidth, rectHeight );
  //fill(resetWhite);
  //
  //
  if ( draw == true && mouseX>drawingSurfaceX && mouseX<drawingSurfaceX+drawingSurfaceWidth && mouseY>drawingSurfaceY && mouseY<drawingSurfaceY+drawingSurfaceHeight && stamp == false && stampR == false) line (mouseX, mouseY, pmouseX, pmouseY);
  if ( draw == true && mouseX>drawingSurfaceX && mouseX<drawingSurfaceX+drawingSurfaceWidth && mouseY>drawingSurfaceY && mouseY<drawingSurfaceY+drawingSurfaceHeight && lineTool == false && stampR == false ) {
      ellipse( mouseX, mouseY, drawingDiameter, drawingDiameter);
  }
  if ( draw == true && mouseX>drawingSurfaceX && mouseX<drawingSurfaceX+drawingSurfaceWidth && mouseY>drawingSurfaceY && mouseY<drawingSurfaceY+drawingSurfaceHeight && lineTool == false && stamp == false ) {
      rect( mouseX, mouseY, drawingDiameter, drawingDiameter );
  }
  //
  //
  //Hover-over
  if ( mouseX>quitButtonX && mouseX<quitButtonX+quitButtonWidth && mouseY>quitButtonY && mouseY<quitButtonY+quitButtonHeight ) {
    buttonFill = blue;
  } else {
    buttonFill = grey;
  }//End Hover-Over
  fill(buttonFill); //2-colours to start, remember that nightMode adds choice
  rect(quitButtonX, quitButtonY, quitButtonWidth, quitButtonHeight);
  rect(lineToolX, lineToolY, lineToolWidth, lineToolHeight);
  rect(stampX, stampY, stampWidth, stampHeight);
  rect(clearButtonX, clearButtonY, clearButtonWidth, clearButtonHeight);
  rect(eraseX, eraseY, eraseWidth, eraseHeight);
  rect(stampRX, stampRY, stampRWidth, stampRHeight);
  rect(thinX, thinY, thinWidth, thinHeight);
  rect(thickX, thickY, thickWidth, thickHeight);
  //rect(tempX, tempY, tempWidth, tempHeight);
  fill(resetButtonColour);
  //
  //ellipse( mouseX, mouseY, drawingDiameter, drawingDiameter); //Example Circle Drawing Tool
  //
  //
  //Text Draw, General Code for any text
  //Note: visualization rectangle is in main program
  fill(black); //Ink, hexidecimal copied from Color Selector
  textAlign (CENTER, CENTER); //Align X&Y, see Processing.org / Reference
  //Values: [LEFT | CENTER | RIGHT] & [TOP | CENTER | BOTTOM | BASELINE]
  textFont(buttonFont, 20); //Change the number until it fits, largest font size
  //
  //Specific Text per button
  text(quitButtonText, quitButtonX, quitButtonY, quitButtonWidth, quitButtonHeight);
  text(lineToolText, lineToolX, lineToolY, lineToolWidth, lineToolHeight);
  text(clearButtonText, clearButtonX, clearButtonY, clearButtonWidth, clearButtonHeight);
  text(eraseText, eraseX, eraseY, eraseWidth, eraseHeight);
  fill(white); //Will change the fill() on all shapes the second time repeated in draw()
  //
  //Text Draw, General Code for any text
  //Note: visualization rectangle is in main program
  fill(black); //Ink, hexidecimal copied from Color Selector
  textAlign (CENTER, CENTER); //Align X&Y, see Processing.org / Reference
  //Values: [LEFT | CENTER | RIGHT] & [TOP | CENTER | BOTTOM | BASELINE]
  textFont(buttonFont, 13); //Change the number until it fits, largest font size
  //
  //Specific Text per button
  text(stampText, stampX, stampY, stampWidth, stampHeight);
  text(stampRText, stampRX, stampRY, stampRWidth, stampRHeight);
  text(thinText, thinX, thinY, thinWidth, thinHeight);
  text(thickText, thickX, thickY, thickWidth, thickHeight);
  //text(tempText, tempX, tempY, tempWidth, tempHeight);
  fill(white); //Will change the fill() on all shapes the second time repeated in draw()
  //
  fill(flower);
  rect(backX, backY, backWidth, backHeight);
  fill(resetWhite);
  fill(white);
  rect(backX1, backY1, backWidth1, backHeight1);
  fill(resetWhite);
  fill(bell);
  rect(backX2, backY2, backWidth2, backHeight2);
  fill(resetWhite);
  //
 if(mousePressed) {
   if ( thin == true && thick == false ) {
          strokeWeight(1); 
          line (mouseX, mouseY, pmouseX, pmouseY);
          ellipse( mouseX, mouseY, drawingDiameter, drawingDiameter);
          rect( mouseX, mouseY, drawingDiameter, drawingDiameter );
          }
 }
  if ( thick == true && thin == false ) {
          strokeWeight(16);
          line (mouseX, mouseY, pmouseX, pmouseY);
          ellipse( mouseX, mouseY, drawingDiameter, drawingDiameter);
          rect( mouseX, mouseY, drawingDiameter, drawingDiameter );
      }  
}
//End draw
//
void keyPressed() {
}//End keyPressed
//
void mousePressed() {
    erase = false;
    thin = false;
    thick = false;
    //tempON = false;
    //rect = false;
     strokeWeight(1);
     if ( mouseX>drawingSurfaceX && mouseX<drawingSurfaceX+drawingSurfaceWidth && mouseY>drawingSurfaceY && mouseY<drawingSurfaceY+drawingSurfaceHeight ) {
      if ( draw == true ) {
      draw = false;
    } else {
      draw = true;
    }
  }//End drawing tools
  //
  if ( draw == true && mouseX>thickX && mouseX<thickX+thickWidth && mouseY>thickY && mouseY<thickY+thickHeight ) {
      if ( thick == true ) {
          thick = false;
      } else {
          thick = true;
          thin = false;
      }
  }
  //
    if ( draw == true &&mouseX>thinX && mouseX<thinX+thinWidth && mouseY>thinY && mouseY<thinY+thinHeight ) {
      if ( thin == true ) {
          thin = false;
      } else {
          thin = true;
          thick = false;
      }
  }
  //
  if ( mouseX>quitButtonX && mouseX<quitButtonX+quitButtonWidth && mouseY>quitButtonY && mouseY<quitButtonY+quitButtonHeight ) exit(); //Quit Button
  //
  //line Tool toggle
   if ( mouseX>lineToolX && mouseX<lineToolX+lineToolWidth && mouseY>lineToolY && mouseY<lineToolY+lineToolHeight ) {
     if ( lineTool == true ) {
       lineTool = false;
      } else {
       lineTool = true;
       stamp = false;
       stampR = false;
       erase = false;
      }
   }//Line Tool
   if ( mouseX>stampX && mouseX<stampX+stampWidth && mouseY>stampY && mouseY<stampY+stampHeight ) {
     if ( stamp == true ) {
       stamp = false;
      } else {
       stamp = true;
       lineTool = false;
       stampR = false;
       erase = false;
      }
   }
   //
   if ( mouseX>stampRX && mouseX<stampRX+stampRWidth && mouseY>stampRY && mouseY<stampRY+stampRHeight ) {
     if ( stampR == true ) {
       stampR = false;
      } else {
       stampR = true;
       lineTool = false;
       stamp = false;
       erase = false;
      }
   }//End circle stamp
 //
   if(mousePressed){
       if ( mouseX>backX && mouseX<backX+backWidth && mouseY>backY && mouseY<backY+backHeight ) {
          fill(flower);
          rect (drawingSurfaceX, drawingSurfaceY, drawingSurfaceWidth, drawingSurfaceHeight);
          fill(resetWhite);
          //
          fill(flower);
          rect(backX, backY, backWidth, backHeight);
          fill(resetWhite);
          fill(white);
          rect(backX1, backY1, backWidth1, backHeight1);
          fill(resetWhite);
          fill(bell);
          rect(backX2, backY2, backWidth2, backHeight2);
          fill(resetWhite);
      }
      //
      if ( mouseX>backX1 && mouseX<backX1+backWidth1 && mouseY>backY1 && mouseY<backY1+backHeight1 ) {
          fill(white);
          rect (drawingSurfaceX, drawingSurfaceY, drawingSurfaceWidth, drawingSurfaceHeight);
          fill(resetWhite);
          //
          fill(flower);
          rect(backX, backY, backWidth, backHeight);
          fill(resetWhite);
          fill(white);
          rect(backX1, backY1, backWidth1, backHeight1);
          fill(resetWhite);
          fill(bell);
          rect(backX2, backY2, backWidth2, backHeight2);
          fill(resetWhite);
      }
      //
      if ( mouseX>backX2 && mouseX<backX2+backWidth2 && mouseY>backY2 && mouseY<backY2+backHeight2 ) {
          fill(bell);
          rect (drawingSurfaceX, drawingSurfaceY, drawingSurfaceWidth, drawingSurfaceHeight);
          fill(resetWhite);
          //
          fill(flower);
          rect(backX, backY, backWidth, backHeight);
          fill(resetWhite);
          fill(white);
          rect(backX1, backY1, backWidth1, backHeight1);
          fill(resetWhite);
          fill(bell);
          rect(backX2, backY2, backWidth2, backHeight2);
          fill(resetWhite);
      }
      //
      if ( mouseX>clearButtonX && mouseX<clearButtonX+clearButtonWidth && mouseY>clearButtonY && mouseY<clearButtonY+clearButtonHeight ) {
        fill(white);
        rect (drawingSurfaceX, drawingSurfaceY, drawingSurfaceWidth, drawingSurfaceHeight);
        fill(resetWhite);
        //
        fill(flower);
        rect(backX, backY, backWidth, backHeight);
        fill(resetWhite);
        //
        fill(white);
        rect(backX1, backY1, backWidth1, backHeight1);
        fill(resetWhite);
        //
        fill(bell);
        rect(backX2, backY2, backWidth2, backHeight2);
        fill(resetWhite);
        //
        strokeWeight(1);
        fill(redC);
        rect(10, 10, 25, 25 );
        fill(blueC );
        rect(35, 10, 25, 25 );
        fill(greenC);
        rect(10, 35, 25, 25);
        fill(yellow);
        rect(35, 35, 25, 25);
        fill(orange);
        rect(10, 60, 25, 25);
        fill(violet);
        rect(35, 60, 25, 25);
        fill(blueGreen);
        rect(10, 85, 25, 25);
        fill(yellowGreen);
        rect(35, 85, 25, 25);
        fill(pink);
        rect(10, 110, 25, 25);
        fill(yellowOrange);
        rect(35, 110, 25, 25);
        fill(white);
        rect(10, 135, 25, 25);
        fill(black);
        rect(35, 135, 25, 25);
      }
   //
   if ( mouseX>eraseX && mouseX<eraseX+eraseWidth && mouseY>eraseY && mouseY<eraseY+eraseHeight ) {
      if ( erase == true ) {
        erase = false;
    } else {
           erase = true;
           }
        }
    //
    //if ( mouseX>=tempX && mouseX<=tempX+tempWidth && mouseY>=tempY && mouseY<=tempY+tempHeight ) rect=true;
    //   
} //End drawing tools
}
//End mousePressed
//
//End MAIN Program

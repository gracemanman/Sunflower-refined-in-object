Sunflower-refined-in-object
===========================

//Man Zhu
//Object related programming for moving flowers

myFlowers[] myFlowers;
color[] colors = new color[3];

//initialize Sunflower object
void setup(){ 
  size(700,500);
  smooth();
  colors[0] = #FE4365;
  colors[1] = #FC9D9A;
  colors[2] = #F9CDAD;
  
  myFlowers = new myFlowers[5];
  for(int i=0; i<5;i++){
   myFlowers[i]=new myFlowers(random(0,width),random(height/2,height),colors[int(random(0,2))]);
  }
}

  
  void draw(){
    background(255);
    fill(#97DEFF);
    rect(0,0,700,300);
    for(int i=0;i<5;i++){
    myFlowers[i].display();
    }
    
  }
  
  //the class name
  class myFlowers{ 
    float tempx;
    float tempy;
    color tempc;
    
    //constructor
    myFlowers(float x, float y, color c){
    tempx=x;
    tempy=y;
    tempc=c;
    }
  
   
    //functionality
    void display(){
      noStroke();
  fill(#C9FFD5);
  rect(tempx, tempy, 5, 125);//the branch of the flower
  fill(#74CEB7);
  ellipse(tempx+25, tempy+100, 50, 20);//the right leaf of the flower
  ellipse(tempx-25, tempy+100, 50, 20);//the left leaf of the flower
  fill(tempc);
  ellipse(tempx, tempy-25, 25, 25);//the upper petal 
  ellipse(tempx, tempy+25, 25, 25);//the lower petal
  ellipse(tempx-25, tempy, 25, 25);//the left petal
  ellipse(tempx+25, tempy, 25, 25);//the right petal
  ellipse((tempx-sin(radians(45))*25), (tempy-sin(radians(45))*25), 25, 25);//the upper left corner petal
  ellipse((tempx+sin(radians(45))*25), (tempy-sin(radians(45))*25), 25, 25);//the upper right corner petal
  ellipse((tempx-sin(radians(45))*25), (tempy+sin(radians(45))*25), 25, 25);//the lower left corner petal
  ellipse((tempx+sin(radians(45))*25), (tempy+sin(radians(45))*25), 25, 25);//the lower right corner petal
  fill(#FFFFCB);
  ellipse(tempx, tempy, 50, 50);//the core of the sunflower
  
  tempy=tempy+1;
     if(tempy>height){
   tempy=height/2;
    }
   
  }
     }

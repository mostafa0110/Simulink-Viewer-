package com.example.demo1;

import javafx.application.Application;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.HBox;
import javafx.scene.layout.Pane;
import javafx.scene.layout.StackPane;
import javafx.scene.paint.Color;
import javafx.scene.paint.ImagePattern;
import javafx.scene.shape.Circle;
import javafx.scene.shape.Polygon;
import javafx.scene.shape.Rectangle;
import javafx.scene.text.Font;
import javafx.scene.text.FontWeight;
import javafx.scene.text.Text;
import javafx.stage.Stage;
import java.io.FileInputStream;
import java.util.ArrayList;//427 get
import java.util.* ;//100,106,302,385
import java.io.IOException;

import javafx.geometry.Point2D ;
public class SimulinkViewer extends Application {
    static ArrayList<Block> blocks = new ArrayList<Block>();
    static ArrayList<Line> lines = new ArrayList<Line>();
    static ArrayList<Line.Branch> branches = new ArrayList<Line.Branch>();
    @Override
    public void start(Stage primarystage) throws IOException {
        Pane pane = new Pane();
        for(int i=0;i<blocks.size();i++)
        {     ImageView imageView2 = new ImageView();
            Rectangle x= new Rectangle( blocks.get(i).getLeft(),blocks.get(i).getTop(),blocks.get(i).getLength() ,blocks.get(i).getHight()) ;
            x.setArcWidth(10);
            x.setArcHeight(10);
            x.setStroke(Color.BLUE);
            x.setFill(Color.TRANSPARENT);
            Text t = new Text (blocks.get(i).getLeft(),blocks.get(i).getBottom()+12,blocks.get(i).getName()) ;
            t.setX((x.getX()+x.getWidth()/2)-t.getLayoutBounds().getWidth() / 2);
            t.setScaleY(1);
            t.setScaleX(0.9);
            StackPane baneh = new StackPane();
            if(Objects.equals(blocks.get(i).getName(), "Add")){
                Image image = new Image(new FileInputStream("C:\\Users\\seif alrahman\\Desktop\\+++.jpg")) ;
                imageView2 =new ImageView(image);

                imageView2.setX(blocks.get(i).getLeft());
                imageView2.setY(blocks.get(i).getTop()) ;


                imageView2.setFitHeight(blocks.get(i).getHight());
                imageView2.setFitWidth(blocks.get(i).getLength());


                pane.getChildren().addAll(imageView2) ;
            }
            else if(Objects.equals(blocks.get(i).getName(), "Constant")){
                Image image = new Image(new FileInputStream("C:\\Users\\seif alrahman\\Desktop\\1.jpg")) ;
                imageView2 =new ImageView(image);
                imageView2.setX(blocks.get(i).getLeft());
                imageView2.setY(blocks.get(i).getTop()) ;
                imageView2.setFitHeight(blocks.get(i).getHight());
                imageView2.setFitWidth(blocks.get(i).getLength());
                pane.getChildren().addAll(imageView2) ;
            }
            else if(Objects.equals(blocks.get(i).getName(), "Scope")){
                Image image = new Image(new FileInputStream("C:\\Users\\seif alrahman\\Desktop\\SCOPE.jpg")) ;
                imageView2 =new ImageView(image);
                imageView2.setX(blocks.get(i).getLeft());
                imageView2.setY(blocks.get(i).getTop()) ;
                imageView2.setFitHeight(blocks.get(i).getHight());
                imageView2.setFitWidth(blocks.get(i).getLength());
                pane.getChildren().addAll(imageView2) ;
            }
            else if(Objects.equals(blocks.get(i).getName(), "Saturation")){
                Image image = new Image(new FileInputStream("C:\\Users\\seif alrahman\\Desktop\\SATURATION.jpg")) ;
                imageView2 =new ImageView(image);
                imageView2.setX(blocks.get(i).getLeft());
                imageView2.setY(blocks.get(i).getTop()) ;
                imageView2.setFitHeight(blocks.get(i).getHight());
                imageView2.setFitWidth(blocks.get(i).getLength());
                pane.getChildren().addAll(imageView2) ;
            }
            else if(Objects.equals(blocks.get(i).getName(), "Unit Delay")){
                Image image = new Image(new FileInputStream("C:\\Users\\seif alrahman\\Desktop\\1overZ.png")) ;
                imageView2 =new ImageView(image);
                imageView2.setX(blocks.get(i).getLeft());
                imageView2.setY(blocks.get(i).getTop()) ;
                imageView2.setFitHeight(blocks.get(i).getHight());
                imageView2.setFitWidth(blocks.get(i).getLength());
                pane.getChildren().addAll(imageView2) ;
            }
            t.setFont(Font.font("Arial", FontWeight.BOLD, 12));
            pane.getChildren().addAll(t,x) ;
        }
        for (Line line : lines) {
            for (int j = 0; j < (line.getPoints().size() - 1); j++) {
                javafx.scene.shape.Line l = new javafx.scene.shape.Line(line.getPoints().get(j).getX(), line.getPoints().get(j).getY(), line.getPoints().get(j + 1).getX(), line.getPoints().get(j + 1).getY());
                if ((!line.getHasBranches()) && (j == (line.getPoints().size() - 2))) {
                    Polygon arrowhead = new Polygon();
                    arrowhead.getPoints().addAll(-2.5, 7.0,
                            3.5, 3.5,
                            -2.5, 0.0);
                    arrowhead.setFill(Color.BLACK);
                    double angle = Math.atan2((l.getEndY() - l.getStartY()), (l.getEndX() - l.getStartX())) * 180 / Math.PI;
                    arrowhead.setLayoutX(l.getEndX() - arrowhead.getBoundsInLocal().getWidth() / 2);
                    arrowhead.setLayoutY(l.getEndY() - arrowhead.getBoundsInLocal().getHeight() / 2);

                    arrowhead.setRotate(angle);
                    pane.getChildren().addAll(l, arrowhead);
                } else {

                    pane.getChildren().addAll(l);
                }
                // Point2D x = new Point2D(1,1) ;

                // pane.getChildren().addAll(l) ;
            }

        }
        for (Line.Branch branch : branches) {
            for (int j = 0; j < (branch.getBranchPoints().size() - 1); j++) {
                javafx.scene.shape.Line l = new javafx.scene.shape.Line(branch.getBranchPoints().get(j).getX(), branch.getBranchPoints().get(j).getY(), branch.getBranchPoints().get(j + 1).getX(), branch.getBranchPoints().get(j + 1).getY());
                Circle c = new Circle(l.getStartX(), l.getStartY(), 2, Color.BLACK);
                if ((j == (branch.getBranchPoints().size() - 2))) {
                    Polygon arrowhead = new Polygon();
                    arrowhead.getPoints().addAll(-2.5, 7.0,
                            3.5, 3.5,
                            -2.5, 0.0);
                    arrowhead.setFill(Color.BLACK);
                    double angle = Math.atan2((l.getEndY() - l.getStartY()), (l.getEndX() - l.getStartX())) * 180 / Math.PI;
                    arrowhead.setLayoutX(l.getEndX() - arrowhead.getBoundsInLocal().getWidth() / 2);
                    arrowhead.setLayoutY(l.getEndY() - arrowhead.getBoundsInLocal().getHeight() / 2);

                    arrowhead.setRotate(angle);
                    pane.getChildren().addAll(l, arrowhead);
                } else {
                    pane.getChildren().addAll(c, l);
                }
//                pane.getChildren().add(l) ;
            }

        }

        Scene scene= new Scene(pane,1500,700) ;
        primarystage.setTitle("Simulink Viewer");
        primarystage.setScene(scene);
        primarystage.show();
    }

    public static void main(String[] args) throws IOException {

        // String fileName = args[0];
        //File file = new File(fileName);
        FileInputStream inputStream = new FileInputStream("C:/Users/seif alrahman/Desktop/Example.mdl");
        StringBuilder stringBuilder = new StringBuilder();
        int d;
        while ((d = inputStream.read()) != -1) {
            stringBuilder.append((char) d);
        }

        String data = stringBuilder.toString();
        Scanner scanner = new Scanner(data);

        while (scanner.hasNextLine()) {
            String satr = scanner.nextLine();
            if (satr.contains("<System>")) {
                break;
            }
        }



        Blockfinder bfinder = new Blockfinder();

        while (scanner.hasNextLine()) {
            String satr = scanner.nextLine();
            if (satr.contains("<Block BlockType=")) {
                boolean mirrored =false ;
                String name = satr.substring(satr.indexOf("me=\"") + 4, satr.indexOf("\" S"));
                String SID = satr.substring(satr.indexOf("SID=\"") + 5, satr.indexOf("\">"));
                String numins = "1", numouts = "1";
                String left = "", top = "", right = "", bottom = "";

                while (!(satr.contains("</Block>"))) {
                    satr = scanner.nextLine();
                    if (satr.contains(" <P Name=\"Ports\">")) {
                        if (satr.contains(",")) {
                            numins = satr.substring(satr.indexOf(">[") + 2, satr.indexOf(","));
                            numouts = satr.substring(satr.indexOf(",") + 2, satr.indexOf("]"));
                        } else {
                            numins = satr.substring(satr.indexOf(">[") + 2, satr.indexOf("]"));
                        }

                    }
                    if(satr.contains(" <P Name=\"BlockMirror\">on")){
                        mirrored=true ;
                    }
                    if (satr.contains("<P Name=\"Position\">")) {
                        String pos = satr.substring(satr.indexOf(">[") + 2, satr.indexOf("]"));

                        int numcommas = 0;
                        for (int i = 0; i < pos.length(); i++) {
                            if (pos.charAt(i) == ',') {
                                numcommas++;
                                i++;
                                continue;
                            }
                            if (numcommas == 0) {
                                left += pos.charAt(i);
                            }
                            if (numcommas == 1) {
                                top += pos.charAt(i);
                            }
                            if (numcommas == 2) {
                                right += pos.charAt(i);
                            }
                            if (numcommas == 3) {
                                bottom += pos.charAt(i);
                            }

                        }
                    }

                }
                int[] arr = new int[4];
                arr[0] = Integer.parseInt(left);
                arr[1] = Integer.parseInt(top);
                arr[2] = Integer.parseInt(right);
                arr[3] = Integer.parseInt(bottom);
                Block bl = new Block(name, Integer.parseInt(SID), Integer.parseInt(numins), Integer.parseInt(numouts), arr,mirrored);
                blocks.add(bl);


                bfinder.addBlock( bl)   ;       ////////////////////newwwww


            } else if (satr.contains("<Line")) {
                int flag = 0;
                String SRC = "";
                String SRCPORT = "";
                String DST = "159326";
                String DSTPORT = "159326";
                ArrayList<Point2D> malhashlazma = new ArrayList<Point2D>();
                Line l1 = new Line(0, 0, 0, 0, malhashlazma);
                ArrayList<String> offsets = new ArrayList<String>();
                while (!(satr.contains("</Line>"))) {
                    satr = scanner.nextLine();
                    if (satr.contains("<P Name=\"Src\"")) {
                        SRC = satr.substring(satr.indexOf(">") + 1, satr.indexOf("#"));
                        SRCPORT = satr.substring(satr.indexOf(":") + 1, satr.indexOf("</P>"));
                    } else if (satr.contains(" <P Name=\"Points\">")) {
                        String Points = satr.substring(satr.indexOf(">[") + 2, satr.indexOf("]</P>"));

                        int counter =0;
                        offsets.add("");
                        for (int i = 0; i < Points.length(); i++) {
                            if (Points.charAt(i) == ',' || Points.charAt(i) == ';') {
                                counter++;
                                offsets.add("");
                                i+=2;
                            }

                            String current = offsets.get(counter);
                            current += Points.charAt(i);
                            offsets.set(counter, current);

                        }
                       /* for(int i =0; i< offsets.size();i++)
                        {
                            System.out.println(offsets.get(i));
                        }*/
                    } else if (satr.contains(" <P Name=\"Dst\">")) {
                        DST = satr.substring(satr.indexOf(">") + 1, satr.indexOf("#"));
                        DSTPORT = satr.substring(satr.indexOf(":") + 1, satr.indexOf("</P>"));
                    }


                    if (satr.contains("<Branch")) {

                        if (flag == 0) {
                            ArrayList<Point2D> offsetspoint = new ArrayList<Point2D>();
                            for (int i = 0; i < offsets.size(); i += 2) {
                                Point2D temp = new Point2D(Integer.parseInt(offsets.get(i)), Integer.parseInt(offsets.get(i + 1)));
                                offsetspoint.add(temp);
                            }

                            l1 = new Line(Integer.parseInt(SRC), Integer.parseInt(SRCPORT), Integer.parseInt(DST), Integer.parseInt(DSTPORT), offsetspoint);
                            lines.add(l1);
                            flag = 1;
                        }
                        ArrayList<String> offsets_branches = new ArrayList<String>();
                        String DSTBR = "", DSTPORTBR = "";
                        int flag2=0;
                        while (!(satr.contains("</Branch>"))) {
                            satr = scanner.nextLine();
                            if (satr.contains("<P Name=\"Points\">")) {
                                offsets_branches.add(satr.substring(satr.indexOf(">[") + 2, satr.indexOf(",")));
                                offsets_branches.add(satr.substring(satr.indexOf(",") + 2, satr.indexOf("]")));
                                flag2=1;
                            }
                            if (satr.contains(" <P Name=\"Dst\">")) {
                                DSTBR = satr.substring(satr.indexOf(">") + 1, satr.indexOf("#"));
                                DSTPORTBR = satr.substring(satr.indexOf(":") + 1, satr.indexOf("</P>"));


                            }
                        }
                        ArrayList<Point2D> branchoffset = new ArrayList<Point2D>();
                        if(flag2==1){
                            Point2D theonlyoffset = new Point2D(Integer.parseInt(offsets_branches.get(0)), Integer.parseInt(offsets_branches.get(1)));
                            branchoffset.add(theonlyoffset) ;
                        }
                        Line.Branch b1 = l1.new Branch(Integer.parseInt(DSTBR), Integer.parseInt(DSTPORTBR), branchoffset);
                        branches.add(b1);
                    }
                }


                if (flag == 0) {
                    ArrayList<Point2D> offsetspoint = new ArrayList<Point2D>();
                    for (int i = 0; i < offsets.size(); i += 2) {
                        Point2D temp = new Point2D(Integer.parseInt(offsets.get(i)), Integer.parseInt(offsets.get(i + 1)));
                        offsetspoint.add(temp);
                    }

                    l1 = new Line(Integer.parseInt(SRC), Integer.parseInt(SRCPORT), Integer.parseInt(DST), Integer.parseInt(DSTPORT), offsetspoint);
                    lines.add(l1);
                    flag = 1;
                }


            }

        }
      /*  System.out.println(blocks.get(2).getOuts(0));
        System.out.println(lines.get(1).getStartPoint());
        System.out.println(lines.get(1).getEndPoint());
*/



        launch();
    }
}




class Line {
    private int srcID;
    private int srcPort;
    private int dstID;
    private boolean hasBranches =true ;
    private int dstPort;
    private Point2D startPoint;
    private Point2D endPoint= new Point2D(0,0);;  //Point2D p1=new Point2D(2,3);

    private ArrayList<Point2D> offset= new ArrayList<Point2D>();
    private ArrayList<Point2D> Points= new ArrayList<Point2D>();

    public Point2D getStartPoint() {
        return startPoint;
    }

    public Point2D getEndPoint() {
        return endPoint;
    }
    public void setHasBranches(){
        if(dstID==159326){
            hasBranches=true ;
        }else{ hasBranches=false; }
    }
    public boolean getHasBranches (){
        return hasBranches ;
    }
    public Line(int srcID , int srcPort , int dstID , int dstPort , ArrayList<Point2D> Offset)
    {   this.srcID=srcID; this.srcPort=srcPort; this.dstID=dstID; this.dstPort=dstPort;

        calcStart();
        endPoint=startPoint;  /// end=end+start

        if(!(Offset.isEmpty()))
        {
            for (int i=0; i<Offset.size() ; i++ ) { offset.add(Offset.get((i))) ;}


            for(int i=0; i<Offset.size();i++) {
                endPoint=endPoint.add( offset.get(i) );
                Points.add(endPoint);             //branch-case:last point added is the last point before branching
            }
        }

        //if empty::
        if( !(dstID==159326 || dstPort==159326 ) )
        {   calcEnd();
            // Points.add(endPoint);
        }
        setHasBranches();
    }


    public ArrayList<Point2D> getPoints() {
        return Points;
    }

    public void calcStart() {
        Block b = Blockfinder.getBlock(srcID);
        if (b != null) {
            startPoint = b.getOutPoint(srcPort);
            Points.add(startPoint);
        } else {
            // Handle case where Block object is null
        }
    }
    public void calcEnd()
    {   Block b=Blockfinder.getBlock(dstID);

        if (b != null) {
            double endy= endPoint.getY();
            endPoint=new Point2D(b.getInPoint(dstPort).getX(),endy);
            Points.add(endPoint);
        } else {
            // Handle case where Block object is null
        }
    }



    class Branch
    {   // We don't include the startpoint in Arr Points
        private Point2D startpoint=endPoint;
        private Point2D endpoint=new Point2D(0,0);
        private ArrayList<Point2D> branchOffset= new ArrayList<Point2D>();
        private int BdstID;
        private int BdstPort;
        private ArrayList<Point2D> BranchPoints= new ArrayList<Point2D>();


        public Branch( int BdstID , int BdstPort , ArrayList<Point2D> branchoffset )
        {
            this.BdstPort=BdstPort;
            this.BdstID=BdstID;
            BranchPoints.add(startpoint);
            endpoint=endpoint.add( startpoint );
            if(!(branchoffset.isEmpty()))
            {
                for(int i=0; i<branchoffset.size();i++) {
                    endpoint=endpoint.add( branchoffset.get(i) );
                    BranchPoints.add(endpoint);
                }
            }
            BcalcEnd();
            BranchPoints.add(endpoint);

        }

        public void BcalcEnd() {
            double endy=endpoint.getY();
            Block b = Blockfinder.getBlock(BdstID);
            endpoint = new Point2D(b.getInPoint(BdstPort).getX(),endy);
        }
        public ArrayList<Point2D> getBranchPoints() {
            return BranchPoints;
        }

    }
}



class Block {

    private String name;
    private boolean mirrored =false ;
    private int SID;
    private int numInports=1;
    private int numOutports=1;
    private double []Pos=new double [4];   ///////0---->left 1----->top
    private Point2D Ins[];
    private Point2D Outs[];

    public Point2D getOuts(int i) {
        return Outs[i];
    }


    public Block(String name, int SID, int numInports, int numOutports , int Position[] , boolean mirrored) {
        this.SID=SID;
        this.name=name;
        this.mirrored=mirrored ;
        this.numInports=numInports;
        this.numOutports=numOutports;
        this.Outs= new Point2D[numOutports] ;
        this.Ins= new Point2D[numInports] ;
        for (int i=0; i<Position.length ; i++ ) { this.Pos[i] = Position[i];}
        calculatePointsIn();
        calculatePointsOut();
    }
    public  double  getLeft (){

        return Pos[0] ;
    }
    public double getBottom(){
        return Pos[3] ;
    }
    public String getName(){
        return  name ;
    }
    public double getTop(){
        return Pos[1];
    }
    public Block(String name, int SID , int Position[] ) {
        this.SID=SID;
        this.name=name;
        this.Outs= new Point2D[numOutports] ;
        this.Ins= new Point2D[numInports] ;
        for (int i=0; i<Position.length ; i++ ) { this.Pos[i] = Position[i];}
        calculatePointsIn();
        calculatePointsOut();
    }



    public int getSID() {return SID;}
    public double getLength(){return (Pos[3]-Pos[1]);}
    public double getHight(){return (Pos[2]-Pos[0]);}


    public Point2D getInPoint(int index) {
        return Ins[index-1];
    }
    public Point2D getOutPoint(int index) {
        return Outs[index-1];
    }

    void calculatePointsOut()
    {
        double spacing=(Pos[3]-Pos[1])/(numOutports+1);
        for(int i=0; i<numOutports ; i++)
        {
            Point2D p=new Point2D(Pos[2], ( Pos[1] + (i+1)*spacing ));
            if(! mirrored)
                Outs[i]=p;
            else Ins[i]=p;
        }
    }
    void calculatePointsIn()
    {
        double spacing=(Pos[3]-Pos[1])/(numInports+1);
        for(int i=0; i<numInports ; i++)
        {
            Point2D p=new Point2D(Pos[0], ( Pos[1] + (i+1)*spacing ));

            if(! mirrored)
                Ins[i]=p;
            else Outs[i]=p;
        }
    }
}


class Blockfinder{
    private static ArrayList<Block> Blocks=new ArrayList<Block>();

    public static Block getBlock(int ID){
        int i=0;
        for(i=0; i<Blocks.size() ; i++)
        {
            if(Blocks.get(i).getSID()==ID) break;
        }
        if (i == Blocks.size()) { // ID not found
            return null;
        }
        return Blocks.get(i);
    }
    public void addBlock(Block b){Blocks.add(b);}
}

class base{
    public double cost = 0.0; //成本
    public double getCost(){
        return this.cost;
    }
}

class LCD extends base{
    public LCD(int size){
        if (size == 10){
            this.cost = (double)2000;
        }
        if (size == 15){
            this.cost = (double)2500;    
        }
        if (size == 17){
            this.cost = (double)3000;
        }
    }
}

class CPU extends base{
    public CPU(double speed){
        if (speed == 1.66){
            this.cost = (double)6000;
        }
        if (speed == 2.2){
            this.cost = (double)8000;
        }
        if (speed == 2.4){
            this.cost = (double)11000;
        }
    }
}

class HD extends base{
    public HD(String size){
        if (size.equals("120G")){
            this.cost = (double)2400;
        }
        if (size .equals("160G")){
            this.cost = (double)2800;
        }
    }
}

class Note{
    LCD lcd;
    CPU cpu;
    HD hd;

    public Note(LCD lcd,CPU cpu,HD hd){
        this.lcd = lcd;
        this.cpu = cpu;
        this.hd = hd;
    }

    double getCost(){
        return (lcd.getCost() + cpu.getCost() + hd.getCost()) * 1.4;
    }

    int getPrice(){
        return ((int)lcd.getCost() + (int)cpu.getCost() + (int)hd.getCost()) * 2;
    }
}

class MiniNote extends Note{
    public MiniNote(){
        super(new LCD(10) , new CPU(1.66) , new HD("120G"));
    }
}

class Note15 extends Note{
    public Note15(){
        super(new LCD(15) , new CPU(2.2) , new HD("160G"));
    }
}


public class J01{
    public static void main(String[] args){
        MiniNote Mini = new MiniNote();
        System.out.println("MiniNote cost:" + Mini.getCost() + ", price:" + Mini.getPrice());
        
        Note15 note15 = new Note15();
        System.out.println("Note15 cost:" + note15.getCost() + ", price:" + note15.getPrice());
    }
}

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

abstract class AllPC{
    abstract double getCost();
    abstract double getPrice();
    public boolean isExpensive(AllPC allpc){
        return this.getPrice() > allpc.getPrice();
    }

}

class Note extends AllPC{
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

    double getPrice(){
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

abstract class PC_MultiPC extends AllPC{
    CPU cpu;
    HD hd;
    int CpuQuantity; //CPU數量
    int HdQuantity; //HD數量

    public PC_MultiPC(CPU cpu , HD hd , int CpuQuantity , int HdQuantity){
        this.cpu = cpu;
        this.hd = hd;
        this.CpuQuantity = CpuQuantity;
        this.HdQuantity = HdQuantity;
    }

    abstract double getCost();
    
    double getPrice(){
        return (cpu.getCost() * CpuQuantity + hd.getCost() * HdQuantity ) * 1.8;
    }

}

class PC extends PC_MultiPC{
    public PC(){
        super (new CPU(2.4) , new HD("160G") , 1 , 1);
    }

    double getCost(){
        return (cpu.getCost() * CpuQuantity + hd.getCost() * HdQuantity ) + 500;
    }
}

class MultiPC extends PC_MultiPC{
    public MultiPC(int CpuQuantity , int HdQuantity){
        super (new CPU(2.4) , new HD("160G") , CpuQuantity , HdQuantity);
    }

    double getCost(){
        return (cpu.getCost() * CpuQuantity + hd.getCost() * HdQuantity ) * 1.2;
    }
}

public class J03 {
    public static void main(String[] args){
        PC pc = new PC();
        Note15 note15 = new Note15();

        if(note15.isExpensive(pc)){
            System.out.println("Note15 is more expensive than PC");
        }
        else{
            System.out.println("PC is more expensive than Note15");
        }
    }
}

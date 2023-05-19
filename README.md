public abstract class Metal {
    public abstract int getEndurance();
}

public class copper extends Metal{

    @Override
    public int getEndurance() {

        return 20;
    }
}

public class iron extends Metal{
    @Override
    public int getEndurance() {

        return 30;
    }
}


public class Plastic {
}

public class steel extends Metal{
    @Override
    public int getEndurance() {

        return 50;
    }
}

public class Sword<T extends Metal> {
    private T material;

    public Sword(T material) {
        this.material = material;
    }

    public boolean isStrongEnough() {
        return material.getEndurance() > 49;
    }
}

  
  public class Test {
    public static void main(String[] args) {
    Sword<steel> sword = new Sword<>(new steel());
    System.out.println("Sword is strong enough: " + sword.isStrongEnough());
}
}


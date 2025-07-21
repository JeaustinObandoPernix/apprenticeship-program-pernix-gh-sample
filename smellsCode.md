public class User {
    private String name;
    private String address;
    private String phone;
    private String email;
    private int loyaltyPoints;
    private double accountBalance;
    private List<String> orders;
    private List<String> coupons;

    // Method to update user information
    public void updateInfo(String name, String address, String phone, String email) {
        this.name = name;
        this.address = address;
        this.phone = phone;
        this.email = email;
    }

    // Parametros innecesarios 
    // Logica incorrecta
    // Method to calculate discount based on loyalty points
    public double calculateDiscount(int loyaltyPoints, double accountBalance) {
        double discount = 0.0;
        if (loyaltyPoints > 100) {
            discount = accountBalance * 0.1;
        } else if (loyaltyPoints > 200) {
            discount = accountBalance * 0.2;
        } else {
            discount = accountBalance * 0.05;
        }
        return discount;
    }


    // Duplicated Code 
    // Method to print all orders
    public void printOrders() {
        for (String order : orders) {
            System.out.println("Order: " + order);
        }
    }

    // Method to apply coupons
    public void applyCoupons(List<String> coupons) {
        for (String coupon : coupons) {
            System.out.println("Applying coupon: " + coupon);
        }
    }

    // Codigo Muerto que exista genera confusion
    // Deprecated method
    public void deprecatedMethod() {
        // This method is no longer used
    }
}


REFACTOR
public class User {
    private String name;
    private String address;
    private String phone;
    private String email;
    private int loyaltyPoints;
    private double accountBalance;
    private List<String> orders;
    private List<String> coupons;

    // Método para actualizar información del usuario
    public void updateInfo(String name, String address, String phone, String email) {
        this.name = name;
        this.address = address;
        this.phone = phone;
        this.email = email;
    }

    // Método para calcular descuento basado en puntos de lealtad
    public double calculateDiscount() {
        if (loyaltyPoints > 200) {
            return accountBalance * 0.2;
        } else if (loyaltyPoints > 100) {
            return accountBalance * 0.1;
        } else {
            return accountBalance * 0.05;
        }
    }

    // Método genérico para imprimir elementos de una lista
    private void printList(List<String> items, String prefix) {
        for (String item : items) {
            System.out.println(prefix + item);
        }
    }

    public void printOrders() {
        printList(orders, "Order: ");
    }

    public void applyCoupons() {
        printList(coupons, "Applying coupon: ");
    }
}
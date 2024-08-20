import java.util.Arrays;

public class MesExo {
    public static void main(String[] args) {
        int[] tab1 = {3, 8, 10, 58, 58, 3};
        int[] filtreTab = new int[tab1.length];
        int[] newTab = new int[tab1.length];
        int newTabIndex = 0;
        
        // Initialiser filtreTab avec des valeurs uniques de tab1
        int filtreTabIndex = 0;
        for (int i = 0; i < tab1.length; i++) {
            boolean isDuplicate = false;
            for (int j = 0; j < filtreTabIndex; j++) {
                if (tab1[i] == filtreTab[j]) {
                    isDuplicate = true;
                    break;
                }
            }
            if (!isDuplicate) {
                filtreTab[filtreTabIndex++] = tab1[i];
            }
        }

        // Copier les valeurs uniques de filtreTab dans newTab
        for (int i = 0; i < filtreTabIndex; i++) {
            newTab[newTabIndex++] = filtreTab[i];
        }

        // Redimensionner newTab pour enlever les valeurs nulles
        newTab = Arrays.copyOf(newTab, newTabIndex);
        
        // Afficher newTab
        System.out.println(Arrays.toString(newTab));
    }
}

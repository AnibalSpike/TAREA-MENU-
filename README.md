# TAREA-MENU-

package application;

import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.BorderPane;
import javafx.stage.Stage;

public class Main extends Application {

    @Override
    public void start(Stage primaryStage) {
        //  BorderPane
        BorderPane root = new BorderPane();

        //  barra de menú
        MenuBar menuBar = new MenuBar();

        // Menú Archivo
        Menu menuFile = new Menu("Archivo");
        MenuItem newFile = new MenuItem("Nuevo");
        MenuItem openFile = new MenuItem("Abrir");
        MenuItem saveFile = new MenuItem("Guardar");
        MenuItem exitFile = new MenuItem("Salir");

        newFile.setOnAction(e -> System.out.println("Nuevo archivo creado"));
        openFile.setOnAction(e -> System.out.println("Archivo abierto"));
        saveFile.setOnAction(e -> System.out.println("Archivo guardado"));
        saveFile.setOnAction(e -> {
            System.out.println("Guardar");
            Alert alert = new Alert(Alert.AlertType.INFORMATION);
            alert.setTitle("Información");
            alert.setHeaderText(null);
            alert.setContentText("Archivo Guardado");
            alert.showAndWait();
        });
        exitFile.setOnAction(e -> primaryStage.close()); 
       //si pusiera el codigo para que me genere un archivo usted tendria que poner el nombre de su pc.

        menuFile.getItems().addAll(newFile, openFile, saveFile, new SeparatorMenuItem(), exitFile);

        // Menú Editar
        Menu menuEdit = new Menu("Editar");
        MenuItem cutEdit = new MenuItem("Cortar");
        MenuItem copyEdit = new MenuItem("Copiar");
        MenuItem pasteEdit = new MenuItem("Pegar");

        cutEdit.setOnAction(e -> System.out.println("Cortar"));
        copyEdit.setOnAction(e -> System.out.println("Copiar"));
        pasteEdit.setOnAction(e -> System.out.println("Pegar"));
        //Mensaje de que el archivo esta copiado
        copyEdit.setOnAction(e -> {
            System.out.println("Copiar");
            Alert alert = new Alert(Alert.AlertType.INFORMATION);
            alert.setTitle("Información");
            alert.setHeaderText(null);
            alert.setContentText("Archivo copiado");
            alert.showAndWait();
        });
        
        //mensaje de que el archivo esta pegado
        pasteEdit.setOnAction(e -> {
            System.out.println("Pegar");
            Alert alert = new Alert(Alert.AlertType.INFORMATION);
            alert.setTitle("Información");
            alert.setHeaderText(null);
            alert.setContentText("Archivo pegado");
            alert.showAndWait();
        });
        

        menuEdit.getItems().addAll(cutEdit, copyEdit, pasteEdit);

        // Menú Ayuda
        Menu menuHelp = new Menu("Ayuda");
        MenuItem aboutHelp = new MenuItem("Acerca de");

        aboutHelp.setOnAction(e -> System.out.println("Mostrar información acerca de"));
        aboutHelp.setOnAction(e -> {
            Alert alert = new Alert(Alert.AlertType.INFORMATION);
            alert.setTitle("Acerca de");
            alert.setHeaderText(null);
            alert.setContentText("Esta es mi tarea profe");
            alert.showAndWait();
        });

        menuHelp.getItems().add(aboutHelp);
        

        // Añadir los menús a la barra de menú
        menuBar.getMenus().addAll(menuFile, menuEdit, menuHelp);

        // Añadir la barra de menú al BorderPane
        root.setTop(menuBar);

        // Crear la escena y añadir el BorderPane
        Scene scene = new Scene(root, 400, 200);

        primaryStage.setTitle("Menú en JavaFX");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}


![image](https://github.com/AnibalSpike/TAREA-MENU-/assets/168206608/0f531e22-8d00-4f9a-a439-84d995fca22c)


![image](https://github.com/AnibalSpike/TAREA-MENU-/assets/168206608/ed5c7ccf-a32e-417c-8ee7-7664ad5270fc)




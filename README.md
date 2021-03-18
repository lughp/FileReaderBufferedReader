# File Reader e Buffered Reader

### FileReader (stream de leitura de caracteres a partir de arquivos)
* https://docs.oracle.com/javase/10/docs/api/java/io/FileReader.html

### BufferedReader (mais rápido)
* https://docs.oracle.com/javase/10/docs/api/java/io/BufferedReader.html
* https://stackoverflow.com/questions/9648811/specific-difference-between-bufferedreader-and-filereader

### IOException (Exception)
* https://docs.oracle.com/javase/10/docs/api/java/io/IOException.html

### Bloco try-with-resources (Java 7 em diante)
* https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html


```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Program {

    public static void main(String[] args) {

        String path = "c:\\temp\\in.txt";

        try (BufferedReader br = new BufferedReader(new FileReader(path))) {
            String line = br.readLine();

            while (line != null) {
                System.out.println(line);
                line = br.readLine();
            }
        }
        catch (IOException e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}
```
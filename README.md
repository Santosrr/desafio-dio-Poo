## Bootcamp Java Developer
Este projeto é um exemplo de aplicação em Java para a gestão de um Bootcamp, incluindo cursos, mentorias e a inscrição e progresso de desenvolvedores (Devs).

Estrutura do Projeto
O projeto é composto pelas seguintes classes principais:

Bootcamp: Representa um bootcamp contendo cursos e mentorias.
Curso: Representa um curso com título, descrição e carga horária.
Mentoria: Representa uma mentoria com título, descrição e data.
Dev: Representa um desenvolvedor que se inscreve em um bootcamp, progride nos cursos e mentorias, e acumula XP.
Código de Exemplo
O código abaixo mostra como criar cursos, mentorias e um bootcamp, além de inscrever dois desenvolvedores no bootcamp e simular seu progresso.

java
Copy code
import br.com.dio.desafio.dominio.Bootcamp;
import br.com.dio.desafio.dominio.Curso;
import br.com.dio.desafio.dominio.Dev;
import br.com.dio.desafio.dominio.Mentoria;

import java.time.LocalDate;

public class Main {
    public static void main(String[] args) {
        Curso curso1 = new Curso();
        curso1.setTitulo("curso java");
        curso1.setDescricao("descrição curso java");
        curso1.setCargaHoraria(8);

        Curso curso2 = new Curso();
        curso2.setTitulo("curso js");
        curso2.setDescricao("descrição curso js");
        curso2.setCargaHoraria(4);

        Mentoria mentoria = new Mentoria();
        mentoria.setTitulo("mentoria de java");
        mentoria.setDescricao("descrição mentoria java");
        mentoria.setData(LocalDate.now());

        Bootcamp bootcamp = new Bootcamp();
        bootcamp.setNome("Bootcamp Java Developer");
        bootcamp.setDescricao("Descrição Bootcamp Java Developer");
        bootcamp.getConteudos().add(curso1);
        bootcamp.getConteudos().add(curso2);
        bootcamp.getConteudos().add(mentoria);

        Dev devCamila = new Dev();
        devCamila.setNome("Camila");
        devCamila.inscreverBootcamp(bootcamp);
        System.out.println("Conteúdos Inscritos Camila:" + devCamila.getConteudosInscritos());
        devCamila.progredir();
        devCamila.progredir();
        System.out.println("-");
        System.out.println("Conteúdos Inscritos Camila:" + devCamila.getConteudosInscritos());
        System.out.println("Conteúdos Concluídos Camila:" + devCamila.getConteúdosConcluidos());
        System.out.println("XP:" + devCamila.calcularTotalXp());

        System.out.println("-------");

        Dev devJoao = new Dev();
        devJoao.setNome("Joao");
        devJoao.inscreverBootcamp(bootcamp);
        System.out.println("Conteúdos Inscritos João:" + devJoao.getConteudosInscritos());
        devJoao.progredir();
        devJoao.progredir();
        devJoao.progredir();
        System.out.println("-");
        System.out.println("Conteúdos Inscritos João:" + devJoao.getConteúdosInscritos());
        System.out.println("Conteúdos Concluidos João:" + devJoao.getConteúdosConcluidos());
        System.out.println("XP:" + devJoao.calcularTotalXp());
    }
}
Como Executar
Certifique-se de ter o JDK instalado na sua máquina.
Compile o código com o seguinte comando:
sh
Copy code
javac -d bin src/br/com/dio/desafio/dominio/*.java src/Main.java
Execute o programa com o seguinte comando:
sh
Copy code
java -cp bin Main
Funcionalidades
Criação de cursos e mentorias.
Inscrição de desenvolvedores em um bootcamp.
Progresso dos desenvolvedores nos cursos e mentorias.
Cálculo do XP acumulado pelos desenvolvedores.
Licença
Este projeto está licenciado sob os termos da licença MIT. Para mais informações, consulte o arquivo LICENSE.

# Orienta-o-a-Objetos-Palavra-chave-This-no-java
Anotações de Orientação a Objetos: Palavra chave this

                                                              Orientação a Objetos: Palavra chave this


De volta ao construtor

Carro(String marca, String modelo) {
    marca = marca;
    modelo = modelo;
}

      ???

A gente no nosso dia a dia utiliza os parâmetros sem under cors então fica marca recebendo marca e isso fica confuso porque você não sabe se é o atributo
marca da classe carro ou se é o parãmetro marca que está recebendo o valor do parâmetro, se o parãmetro recebe o valor do atributo o atributo que recebe o
valor do parâmetro, é contrutores geralmente a gente faz o atributo recebendo o valor do parâmetro e isso fica confuso pra gentem, como é que a genteresolve
isso e tranforma isso em um código mais elegante?

Usando o this

Carro(String marca, String modelo) {
    this.marca = marca;
    this.modelo = modelo;
}

É utilizando o this então a gente coloca o this.marca que aí vai referênciar a um atributo da classe e o this.modelo que vai referênciar ao atributo modelo
da classe então ambos os atributos vão receber os respectivos parâmetros que tem o mesmo nome porém fica muito mais claro fica totalmente separada pra gente

this
.Referencia atributos e métodos da própria classe

O que o this na verdade está fazendo? ele referencia os atributos e métodos da própria classe.


Carro(String marca, String modelo) {
    this.morca = marca;
    this.modelo = modelo;
}

Carro(){
    this("Fiat","Uno")
}


Uma outra maneira da gente referenciar o this também é que por exemplo a gente tem um construtor que tem recebe os parâmetros e dentro do construtor padrão a
gente quer referenciar aquele construtor e aí simplesmente a gente utiliza o this, isso é muito legal na teoria.


void exibirAutonomia2(){
    System.out.print1n("A autonomia do carro é: " + this.obterAutonomia2() + ~ km");
}

double obterAutonomia2(){
    return this.capCombustivel * this.consumoConbustivel;
}


Além de referência outro construtor a gente também pode utilizar isso dentro dos métodos então se você quiser deixar bem explícito que o método que você está
chamando é daquela própria classe você pode colocar o this antes dele e a mesma coisa você pode dentro de métodos tabém, fazer a referência this.atributos
como no exemplo acima.

Ex:

package com.madu.poo.palavra.chave.This;

public class Carro {

	String marca;
	String modelo;
    int numPassageiros;
	double capCombustivel;
	double consumoCombustivel;
			
	public Carro(String marca, String modelo, int numPassageiros, double capCombustivel, double consumoCombustivel) {
		this.marca = marca;
		this.modelo = modelo;
		this.numPassageiros = numPassageiros;
		this.capCombustivel = capCombustivel;
		this.consumoCombustivel = consumoCombustivel;
	}

	public Carro() { }
	
	public Carro(String marca, String modelo, int numPassageiros) {
		this.marca = marca;
		this.modelo = modelo;
		this.numPassageiros = numPassageiros;
		System.out.println("Chamando o construtor com 3 parâmetros");
	}

	public Carro(String marca, String modelo) {
		this(marca, modelo, 10);
		System.out.println("Chamando o construtor com 2 parâmetros");
	}

	void exibirAutonomia() {
	System.out.println("A autonomia do carro é: " + this.capCombustivel * this.consumoCombustivel + " km");
	}
			
    double obterautonomia() {
				
		System.out.println("Método obterAltonomia foi chamado.");
				
		return this.capCombustivel * this.consumoCombustivel;
	}
		
	double calcularCombustivel(double km) {
		
		double qtdCombustivel = km/this.consumoCombustivel;
		
		return qtdCombustivel;
	}
}

Ex:

package com.madu.poo.palavra.chave.This;

public class TesteCarro {

	public static void main(String[] args) {
		
		Carro van = new Carro("Fiat", "Ducato");
		
		System.out.println(van.numPassageiros);
	}

}


Console:

Chamando o construtor com 3 par�metros
Chamando o construtor com 2 par�metros
10

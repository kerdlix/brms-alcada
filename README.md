# BRMS Cálculo de Alçada

## Variáveis de entrada para cada regra
* Classificação Cliente
* Vencimento Operação
* Valor Operação
* Indicador Possui Garantia
* Atividade
* País

## Construção

### 1) Organizational Units
<p align="center"><img src="/images/00.png?raw=true"></p>

### 2) Project
<p align="center"><img src="/images/01.png?raw=true"></p>
<p align="center"><img src="/images/02.png?raw=true"></p>

### 3) Data Object
<p align="center"><img src="/images/10.png?raw=true"></p>
<p align="center"><img src="/images/11.png?raw=true"></p>
<p align="center"><img src="/images/12.png?raw=true"></p>
<p align="center"><img src="/images/13.png?raw=true"></p>
<p align="center"><img src="/images/14.png?raw=true"></p>
<p align="center"><img src="/images/15.png?raw=true"></p>

### 4) Ruleflow
<p align="center"><img src="/images/03.png?raw=true"></p>

### 5) Grupo alcadaEspecifica
<p align="center"><img src="/images/06.png?raw=true"></p>

### 6) Grupo grupo
<p align="center"><img src="/images/06.png?raw=true"></p>
<p align="center"><img src="/images/07.png?raw=true"></p>
<p align="center"><img src="/images/08.png?raw=true"></p>
<p align="center"><img src="/images/09.png?raw=true"></p>

### 7) Grupo cartas
<p align="center"><img src="/images/17.png?raw=true"></p>
<p align="center"><img src="/images/18.png?raw=true"></p>
<p align="center"><img src="/images/19.png?raw=true"></p>
<p align="center"><img src="/images/20.png?raw=true"></p>
<p align="center"><img src="/images/21.png?raw=true"></p>
<p align="center"><img src="/images/22.png?raw=true"></p>
<p align="center"><img src="/images/23.png?raw=true"></p>
<p align="center"><img src="/images/24.png?raw=true"></p>
<p align="center"><img src="/images/25.png?raw=true"></p>
<p align="center"><img src="/images/26.png?raw=true"></p>
<p align="center"><img src="/images/27.png?raw=true"></p>
<p align="center"><img src="/images/28.png?raw=true"></p>
<p align="center"><img src="/images/29.png?raw=true"></p>

### 8) Grupo atividadesRestritivas
<p align="center"><img src="/images/16.png?raw=true"></p>

### 9) Grupo priorizarComite
<p align="center"><img src="/images/30.png?raw=true"></p>
<p align="center"><img src="/images/31.png?raw=true"></p>

### 10) Grupo calcularComite
<p align="center"><img src="/images/04.png?raw=true"></p>

### 11) Grupo comiteGrupo
<p align="center"><img src="/images/05.png?raw=true"></p>

### 12) Decision Server
<p align="center"><img src="/images/32.png?raw=true"></p>

### 13) Cenários de testes
<p align="center"><img src="/images/33.png?raw=true"></p>
<p align="center"><img src="/images/34.png?raw=true"></p>
<p align="center"><img src="/images/35.png?raw=true"></p>
<p align="center"><img src="/images/36.png?raw=true"></p>
<p align="center"><img src="/images/37.png?raw=true"></p>


## Execução dos Testes

### URL Post
http://localhost:8080/kie-server/services/rest/server/containers/instances/alcada

### Teste 1
```
<batch-execution lookup="mySession">
<insert out-identifier="a1">
	<com.redhat.alcada.Alcada>
		<classificacaoCliente>BOM</classificacaoCliente>
		<vencimentoOperacao>11</vencimentoOperacao>
		<valorOperacao>3100</valorOperacao>
		<indicadorPossuiGarantia>true</indicadorPossuiGarantia>
		<atividade>PETROLEO</atividade>
		<pais>BRASIL</pais>
	</com.redhat.alcada.Alcada>
</insert>
<start-process processId="alcada.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

### Teste 2
```
<batch-execution lookup="mySession">
<insert out-identifier="a1">
	<com.redhat.alcada.Alcada>
		<classificacaoCliente>REGULAR</classificacaoCliente>
		<vencimentoOperacao>20</vencimentoOperacao>
		<valorOperacao>850</valorOperacao>
		<indicadorPossuiGarantia>false</indicadorPossuiGarantia>
		<atividade>PETROLEO</atividade>
		<pais>BRASIL</pais>
	</com.redhat.alcada.Alcada>
</insert>
<start-process processId="alcada.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

### Teste 3
```
<batch-execution lookup="mySession">
<insert out-identifier="a1">
	<com.redhat.alcada.Alcada>
		<classificacaoCliente>OTIMO</classificacaoCliente>
		<vencimentoOperacao>8</vencimentoOperacao>
		<valorOperacao>4000</valorOperacao>
		<indicadorPossuiGarantia>false</indicadorPossuiGarantia>
		<atividade>TELEVISAO</atividade>
		<pais>BRASIL</pais>
	</com.redhat.alcada.Alcada>
</insert>
<start-process processId="alcada.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

### Teste 4
```
<batch-execution lookup="mySession">
<insert out-identifier="a1">
	<com.redhat.alcada.Alcada>
		<classificacaoCliente>PESSIMO</classificacaoCliente>
		<vencimentoOperacao>40</vencimentoOperacao>
		<valorOperacao>30000</valorOperacao>
		<indicadorPossuiGarantia>true</indicadorPossuiGarantia>
		<atividade>GOVERNO</atividade>
		<pais>BRASIL</pais>
	</com.redhat.alcada.Alcada>
</insert>
<start-process processId="alcada.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

### Teste 5
```
<batch-execution lookup="mySession">
<insert out-identifier="a1">
	<com.redhat.alcada.Alcada>
		<classificacaoCliente>BOM</classificacaoCliente>
		<vencimentoOperacao>40</vencimentoOperacao>
		<valorOperacao>2000</valorOperacao>
		<indicadorPossuiGarantia>true</indicadorPossuiGarantia>
		<atividade>GOVERNO</atividade>
		<pais>BRASIL</pais>
	</com.redhat.alcada.Alcada>
</insert>
<start-process processId="alcada.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

### Teste 6
```
<batch-execution lookup="mySession">
<insert out-identifier="a1">
	<com.redhat.alcada.Alcada>
		<classificacaoCliente>PESSIMO</classificacaoCliente>
		<vencimentoOperacao>40</vencimentoOperacao>
		<valorOperacao>500</valorOperacao>
		<indicadorPossuiGarantia>true</indicadorPossuiGarantia>
		<atividade>GOVERNO</atividade>
		<pais>EQUADOR</pais>
	</com.redhat.alcada.Alcada>
</insert>
<start-process processId="alcada.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

### Teste 7
```
<batch-execution lookup="mySession">
<insert out-identifier="a1">
	<com.redhat.alcada.Alcada>
		<classificacaoCliente>REGULAR</classificacaoCliente>
		<vencimentoOperacao>5</vencimentoOperacao>
		<valorOperacao>600</valorOperacao>
		<indicadorPossuiGarantia>false</indicadorPossuiGarantia>
		<atividade>GOVERNO</atividade>
		<pais>PARAGUAI</pais>
	</com.redhat.alcada.Alcada>
</insert>
<start-process processId="alcada.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```

### Teste 8
```
<batch-execution lookup="mySession">
<insert out-identifier="g1">
	<com.redhat.alcada.Grupo>
		<elementos>
			<com.redhat.alcada.Elemento>
				<nome>A</nome>
				<pais>BRASIL</pais>
				<classificacao>BOM</classificacao>
				<valorOperacao>2000</valorOperacao>
				<vencimentoOperacao>12</vencimentoOperacao>
			</com.redhat.alcada.Elemento>
			<com.redhat.alcada.Elemento>
				<nome>B</nome>
				<pais>PARAGUAI</pais>
				<classificacao>BOM</classificacao>
				<valorOperacao>800</valorOperacao>
				<vencimentoOperacao>20</vencimentoOperacao>
			</com.redhat.alcada.Elemento>
			<com.redhat.alcada.Elemento>
				<nome>C</nome>
				<pais>BRASIL</pais>
				<classificacao>REGULAR</classificacao>
				<valorOperacao>400</valorOperacao>
				<vencimentoOperacao>25</vencimentoOperacao>
			</com.redhat.alcada.Elemento>
			<com.redhat.alcada.Elemento>
				<nome>D</nome>
				<pais>PARAGUAI</pais>
				<classificacao>BOM</classificacao>
				<valorOperacao>300</valorOperacao>
				<vencimentoOperacao>40</vencimentoOperacao>
			</com.redhat.alcada.Elemento>
			<com.redhat.alcada.Elemento>
				<nome>E</nome>
				<pais>EQUADOR</pais>
				<classificacao>BOM</classificacao>
				<valorOperacao>300</valorOperacao>
				<vencimentoOperacao>40</vencimentoOperacao>
			</com.redhat.alcada.Elemento>
		</elementos>		
	</com.redhat.alcada.Grupo>
</insert>
<start-process processId="alcada.Fluxo">
</start-process>
<fire-all-rules />
</batch-execution>
```



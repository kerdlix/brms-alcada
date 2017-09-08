# BRMS Cálculo de Alçada

## Variáveis de entrada para cada regra
* Classificação Cliente
* Vencimento Operação
* Valor Operação
* Indicador Possui Garantia
* Atividade
* País

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

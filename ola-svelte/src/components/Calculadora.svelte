<script lang="ts">
import Botao from "./Botao.svelte";
import Linha from "./Linha.svelte";
import CalculadoraModel from "./model/CalculadoraModel";
import Tela from "./Tela.svelte";

    let calc = new CalculadoraModel()

    const numeroDigitado = (num: string) => calc = calc.numeroDigitado(num)
    const pontoDigitado = () => calc = calc.pontoDigitado()
    const operacaoDigitada = (op: string) => calc = calc.operacaoDigitada(op)
    const calcular = () => calc = calc.calcular()
    const limpar = () => calc = calc.limpar()


</script>

<div class="calculadora">
    <Tela valor={calc.valor}/>
    <Linha>
        <Botao destaque triplo texto ="AC" onClick={limpar}/>
        <Botao operacao texto="/" onClick={operacaoDigitada}/>
    </Linha>
    <Linha>
        <Botao texto="7" onClick={num => calc = calc.numeroDigitado(num)} />
        <Botao texto="8" onClick={num => calc = calc.numeroDigitado(num)} />
        <Botao texto="9" onClick={num => calc = calc.numeroDigitado(num)} />
        <Botao operacao texto="*" onClick={operacaoDigitada}/>
    </Linha>
    <Linha>
        <Botao texto="4" onClick={num => calc = calc.numeroDigitado(num)}/>
        <Botao texto="5" onClick={num => calc = calc.numeroDigitado(num)}/>
        <Botao texto="6" onClick={num => calc = calc.numeroDigitado(num)}/>
        <Botao operacao texto="+" onClick={operacaoDigitada}/>
    </Linha>
    <Linha>
        <Botao texto="1" onClick={num => calc = calc.numeroDigitado(num)}/>
        <Botao texto="2" onClick={num => calc = calc.numeroDigitado(num)}/>
        <Botao texto="3" onClick={num => calc = calc.numeroDigitado(num)}/>
        <Botao operacao texto="-" onClick={operacaoDigitada}/>
    </Linha>
    <Linha>
        <Botao duplo texto="0" onClick={num => calc = calc.numeroDigitado(num)}/>
        <Botao texto="," onClick={pontoDigitado}/>
        <Botao destaque texto="=" onClick={calcular}/>
    </Linha>
</div>

<style>
    .calculadora {
        background-color: var(--cor-fundo);
        height: 250px;
        width: 250px;
        padding: 10px;
        border-radius: 10px;

        display: flex;
        flex-direction: column;
    }

</style>
document.addEventListener("DOMContentLoaded", function () {
    const calcularBtn = document.getElementById("calcular");
    calcularBtn.addEventListener("click", calcularSubrede);

    function calcularSubrede() {
        const ipInput = document.getElementById("ip");
        const mascaraSelect = document.getElementById("mascara");
        const enderecoRedeSpan = document.getElementById("endereco-rede");
        const enderecoBroadcastSpan = document.getElementById("endereco-broadcast");
        const qtdHostsSpan = document.getElementById("qtd-hosts");

        const ip = ipInput.value;
        const mascara = mascaraSelect.value;

        // Realize os cálculos de sub-rede aqui
        // Exemplo simples: apenas mostre os valores de IP, máscara, endereço de rede, endereço de broadcast e quantidade de hosts
        enderecoRedeSpan.textContent = calcularEnderecoRede(ip, mascara);
        enderecoBroadcastSpan.textContent = calcularEnderecoBroadcast(ip, mascara);
        qtdHostsSpan.textContent = calcularQuantidadeHosts(mascara);
    }

    function calcularEnderecoRede(ip, mascara) {
        // Implemente a lógica para calcular o endereço de rede aqui
        // Este é apenas um exemplo simples
        return "Endereço de Rede Calculado";
    }

    function calcularEnderecoBroadcast(ip, mascara) {
        // Implemente a lógica para calcular o endereço de broadcast aqui
        // Este é apenas um exemplo simples
        return "Endereço de Broadcast Calculado";
    }

    function calcularQuantidadeHosts(mascara) {
        // Implemente a lógica para calcular a quantidade de hosts aqui
        // Este é apenas um exemplo simples
        return "Quantidade de Hosts Calculada";
    }
});

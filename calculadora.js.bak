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
        const { enderecoRede, enderecoBroadcast, qtdHosts } = calcularSubredeCompleta(ip, mascara);

        enderecoRedeSpan.textContent = enderecoRede;
        enderecoBroadcastSpan.textContent = enderecoBroadcast;
        qtdHostsSpan.textContent = qtdHosts;
    }

    function calcularSubredeCompleta(ip, mascara) {
        // Implemente a lógica para calcular endereço de rede, endereço de broadcast e quantidade de hosts aqui
        const ipParts = ip.split('.');
        const mascaraParts = mascara.split('.');

        const enderecoRede = ipParts.map((part, index) => (part & mascaraParts[index]).toString()).join('.');
        const enderecoBroadcast = ipParts.map((part, index) => ((part | ~mascaraParts[index]) & 255).toString()).join('.');

        const qtdHosts = Math.pow(2, 32 - mascaraToCIDR(mascara)) - 2;

        return { enderecoRede, enderecoBroadcast, qtdHosts };
    }

    function mascaraToCIDR(mascara) {
        return mascara.split('.').map(part => (part >>> 0).toString(2)).join('').split('1').length - 1;
    }
});

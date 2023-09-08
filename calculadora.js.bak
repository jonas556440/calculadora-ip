document.addEventListener("DOMContentLoaded", function () {
    var calcularButton = document.getElementById("calcularButton");
    calcularButton.addEventListener("click", calcular);
});

function calcular() {
    var ip = document.getElementById("ip").value;
    var mascaraInput = document.getElementById("mascara").value;
    var mascara = mascaraInput.includes("/") ? cidrToMascara(mascaraInput) : mascaraInput;

    // Lógica de cálculo dos resultados
    var enderecoRede = calcularEnderecoRede(ip, mascara);
    var enderecoBroadcast = calcularEnderecoBroadcast(ip, mascara);
    var qtdRede = calcularQuantidadeRede(mascara);
    var qtdHost = calcularQuantidadeHost(mascara);
    var classeIP = determinarClasseIP(ip);

    // Atualizar os resultados
    document.getElementById("enderecoRede").textContent = enderecoRede;
    document.getElementById("enderecoBroadcast").textContent = enderecoBroadcast;
    document.getElementById("qtdRede").textContent = qtdRede;
    document.getElementById("qtdHost").textContent = qtdHost;
    document.getElementById("classeIP").textContent = classeIP;
}

function calcularEnderecoRede(ip, mascara) {
    var ipArray = ip.split(".");
    var mascaraArray = mascara.split(".");
    var enderecoRedeArray = [];

    for (var i = 0; i < 4; i++) {
        enderecoRedeArray.push(ipArray[i] & mascaraArray[i]);
    }

    return enderecoRedeArray.join(".");
}

function calcularEnderecoBroadcast(ip, mascara) {
    var ipArray = ip.split(".");
    var mascaraArray = mascara.split(".");
    var enderecoBroadcastArray = [];

    for (var i = 0; i < 4; i++) {
        enderecoBroadcastArray.push(ipArray[i] | ~mascaraArray[i]);
    }

    return enderecoBroadcastArray.join(".");
}

function calcularQuantidadeRede(mascara) {
    var mascaraArray = mascara.split(".");
    var qtdRede = 1;

    for (var i = 0; i < 4; i++) {
        qtdRede *= 256 - parseInt(mascaraArray[i]);
    }

    return qtdRede;
}

function calcularQuantidadeHost(mascara) {
    return calcularQuantidadeRede(mascara) - 2;
}

function cidrToMascara(cidr) {
    var prefix = parseInt(cidr.split("/")[1]);
    var mascaraArray = [0, 0, 0, 0];

    for (var i = 0; i < prefix; i++) {
        mascaraArray[Math.floor(i / 8)] += 1 << (7 - (i % 8));
    }

    return mascaraArray.join(".");
}

function determinarClasseIP(ip) {
    var primeiroOcteto = parseInt(ip.split(".")[0]);

    if (primeiroOcteto >= 1 && primeiroOcteto <= 126) {
        return "Classe A";
    } else if (primeiroOcteto >= 128 && primeiroOcteto <= 191) {
        return "Classe B";
    } else if (primeiroOcteto >= 192 && primeiroOcteto <= 223) {
        return "Classe C";
    } else if (primeiroOcteto >= 224 && primeiroOcteto <= 239) {
        return "Classe D (Multicast)";
    } else if (primeiroOcteto >= 240 && primeiroOcteto <= 255) {
        return "Classe E (Reservado)";
    } else {
        return "Inválido";
    }
}

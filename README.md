Conversiones de tiempo en JS
======

Esta simple funciones me permite hacer convenciones en tiempo real, es decir si tengo 60 min la función HoratoHoraReal me retorna 1:00

function SegundoToMilesegundo(seg) {
    return seg*1000;
};
function horasToMin(hora) {
    return (hora * 60) / 1;
};
function MinToHoras(min) {
    return (min * 1) / 60;
};
function HoratoHoraReal(h) {
    hAux = parseInt(h);
    m = h - hAux;
    m = horasToMin(m);
    m = Math.round(m);
    if (m == 60) {
        m = 0;
        hAux++;
    }
    if (hAux <= 9)
        hAux = "0" + hAux.toString();
    if (m <= 9)
        m = "0" + m.toString();
    return hAux + ":" + m;
};
function MinutotoHoraReal(m) {
    return HoratoHoraReal(m / 60);
};
function HoraRealtoMinuto(hReal) {
    aux = hReal.split(":");
    m = horasToMin(parseFloat(aux[0])) + parseFloat(aux[1]);
    return m;
};
function HoraRealtoHorao(hReal) {
    aux = hReal.split(":");
    h = parseFloat(aux[0]) + MinToHoras(parseFloat(aux[1]));
    return h;
};

# Tugas-14-Pemograman-Mobile
const fNama = document.forms['Irwansyah Novendra'];
let nama, penghasilan, pengeluaran, lamakerja, hasilZakat;

fNama.addEventListener('submit', function(e) {

    e.preventDefault();
    nama = fNama.querySelector('#name').value; // console.log(nama)
    penghasilan = fNama.querySelector('#penghasilan').value; //console.log(penghasilan)
    pengeluaran = fNama.querySelector('#pengeluaran').value; // console.log(pengeluaran)
    lamakerja = fNama.querySelector('#lamakerja').value; // console.log(lamakerja)

    // setting kalkulator
    let haul = 40000000;
    let penghasilanTahunan = penghasilan * 12;
    let pengeluaranTahunan = pengeluaran * 12;
    let totalHarta = penghasilanTahunan - pengeluaranTahunan;
    let nilaiZakat = 2.5 / 100 * totalHarta;

    hasilZakat = document.querySelector('#hasil');
    hasilZakat.style.display = 'block';
    
    // logic condition
    if(lamakerja < 12){
        document.querySelector('#hasil div h2').innerHTML = `'${nama}' belum wajib berzakat.`;
        document.getElementById('form').style.display = 'none';
    }
    else if(penghasilanTahunan < pengeluaranTahunan) {
        document.querySelector('#hasil div h2').innerHTML = `'${nama}' terlalu boros, besar pasak dari pada tiang.`;
        document.getElementById('form').style.display = 'none';
    }
    else if(totalHarta < haul && lamakerja >= 12) {
        document.querySelector('#hasil div h2').innerHTML = `'${nama}' belum wajib berzakat.`;
        document.getElementById('form').style.display = 'none';
    }
    else {
        document.querySelector('#hasil div h2').innerHTML = `Zakat yang harus '${nama}' bayarkan adalah Rp.${nilaiZakat},- dalam satu tahun.`;
        document.getElementById('form').style.display = 'none';
    }

});

// ubah logo
const logoBw = document.getElementById('img-logo');
logoBw.addEventListener('mouseover', function() {
    logoBw.src = 'img/logo.png';
});

logoBw.addEventListener('mouseout', function() {
    logoBw.src = 'img/logo-bw.png';
});
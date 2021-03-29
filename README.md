# PBOFS112B-2014436267-LATIHAN51

/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

/**
 *
 * @author ASUS
 * Nama     : Caterina Vinanti
 * Kelas    : PBO FS112B
 * NIM      : 2014436267
 * Deskripsi Prpgram : Program ini berisi tentang Gaji Karyawan
 */


import java.util.Scanner;

class Karyawan {
    String nik, nama, jabatan;
    int golongan;
    
    void setNik(String nik) {
        this.nik = nik;
    }
    
    String getNik() {
        return this.nik;
    }
    
    void setNama(String nama) {
        this.nama = nama;
    }
    
    String getNama() {
        return this.nama;
    }
    
    void setJabatan(String jabatan) {
        this.jabatan = jabatan;
    }
    
    String getJabatan() {
        return this.jabatan;
    }
    
    void setGolongan(int golongan) {
        this.golongan = golongan;
    }
    
    int getGolongan() {
        return this.golongan;
    }
}

class Manager {
    int kehadiran;
    float tunjanganGolongan, tunjanganJabatan, tunjanganKehadiran;
    
    void setKehadiran(int kehadiran) {
        this.kehadiran = kehadiran;
    }
    
    int getKehadiran() {
        return this.kehadiran;
    }
    
    float tunjanganKehadiran(int hadir) {
        this.tunjanganKehadiran = hadir * 10000;
        return this.tunjanganKehadiran;
    }
    
    float tunjanganJabatan(String jabatan) {
        float jab;
        if ("manager".equals(jabatan.toLowerCase())) {
            jab = 2000000;
        } else if("kabag".equals(jabatan.toLowerCase())) {
            jab = 1000000;
        } else {
            jab = 0;
        }
        this.tunjanganJabatan = jab;
        
        return this.tunjanganJabatan;
    }
    
    float tunjanganGolongan(int golongan) {
        float biaya;
        switch(golongan) {
            case 1:
                biaya = 500000;
                break;
            case 2:
                biaya = 1000000;
                break;
            case 3:
                biaya = 1500000;
                break;
            default:
                biaya = 0;
                break;
        }
        this.tunjanganGolongan = biaya;
        
        return this.tunjanganGolongan;
    }
    
    float gajiTotal() {
        return this.tunjanganKehadiran + this.tunjanganJabatan + this.tunjanganGolongan;
    }
}

/**
 *
 * @author eLx
 */
public class PBOFS112B_2014436267_Latihan51_GajiKaryawan {

    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        // TODO code application logic here
        Karyawan karyawan = new Karyawan();
        Manager manager = new Manager();
        Scanner scan = new Scanner(System.in);
        System.out.println("====Program Perhitungan Gaji Karyawan====");
        System.out.print("Masukkan NIK : ");
        karyawan.setNik(scan.nextLine());
        System.out.print("Masukkan Nama : ");
        karyawan.setNama(scan.nextLine());
        System.out.print("Masukkan Golongan (1/2/3) : ");
        karyawan.setGolongan(scan.nextInt());
        Scanner scan2 = new Scanner(System.in);
        System.out.print("Masukkan Jabatan (Manager/Kabag) : ");
        karyawan.setJabatan(scan2.nextLine());
        System.out.print("Masukkan Jumlah Kehadiran : ");
        manager.setKehadiran(scan2.nextInt());
        System.out.println("");
        System.out.println("====Hasil Perhitungan====");
        System.out.println("NIK     : " + karyawan.getNik());
        System.out.println("NAMA    : " + karyawan.getNama());
        System.out.println("GOLONGAN: " + karyawan.getGolongan());
        System.out.println("JABATAN : " + karyawan.getJabatan());
        System.out.println("");
        System.out.println("TUNJANGAN GOLONGAN      : " + manager.tunjanganGolongan(karyawan.getGolongan()));
        System.out.println("TUNJANGAN JABATAN       : " + manager.tunjanganJabatan(karyawan.getJabatan()));
        System.out.println("TUNJANGAN KEHADIRAN     : " + manager.tunjanganKehadiran(manager.getKehadiran()));
    }
    
}





public class SinhVien {
    private int maSV;
    private String hoTen;
    private String diaChi;
    private String soDienThoai;
    
    public SinhVien() {}
    
    public SinhVien(int maSV, String hoTen, String diaChi, String soDienThoai) {
        this.maSV = maSV;
        this.hoTen = hoTen;
        this.diaChi = diaChi;
        this.soDienThoai = soDienThoai;
    }
    
    public int getMaSV() {
        return maSV;
    }
    
    public void setMaSV(int maSV) {
        this.maSV = maSV;
    }
    
    public String getHoTen() {
        return hoTen;
    }
    
    public void setHoTen(String hoTen) {
        this.hoTen = hoTen;
    }
    
    public String getDiaChi() {
        return diaChi;
    }
    
    public void setDiaChi(String diaChi) {
        this.diaChi = diaChi;
    }
    
    public String getSoDienThoai() {
        return soDienThoai;
    }
    
    public void setSoDienThoai(String soDienThoai) {
        this.soDienThoai = soDienThoai;
    }
    
    @Override
    public String toString() {
        return "MaSV: " + maSV + ", Ho ten: " + hoTen + ", Dia chi: " + diaChi + ", So dien thoai: " + soDienThoai;
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Nhap so sinh vien: ");
        int n = scanner.nextInt();
        
        SinhVien[] danhSachSV = new SinhVien[n];
        
        for (int i = 0; i < n; i++) {
            System.out.println("Nhap thong tin sinh vien thu " + (i + 1) + ":");
            System.out.print("Ma SV: ");
            int maSV = scanner.nextInt();
            scanner.nextLine();
            System.out.print("Ho ten: ");
            String hoTen = scanner.nextLine();
            System.out.print("Dia chi: ");
            String diaChi = scanner.nextLine();
            System.out.print("So dien thoai: ");
            String soDienThoai = scanner.nextLine();
            
            SinhVien sv = new SinhVien(maSV, hoTen, diaChi, soDienThoai);
            danhSachSV[i] = sv;
        }
        
        for (int i = 0; i < n - 1; i++) {
            for (int j = i + 1; j < n; j++) {
                if (danhSachSV[i].getMaSV() > danhSachSV[j].getMaSV()) {
                    SinhVien temp = danhSachSV[i];
                    danhSachSV[i] = danhSachSV[j];
                    danhSachSV[j] = temp;
                }
            }
        }
        
        System.out.println("Danh sach sinh vien:");
        for (int i = 0; i < n; i++) {
            System.out.println(danhSachSV[i]);
        }
    }
}

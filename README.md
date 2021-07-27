# postgresql13-ansible
Postgresql13 manage with Ansible  

01-playbook-installpackages.yaml; postgresql13 için repo ve gpg key import eder, apt update işlemi gerçekleşir, loopta belirtilen paketleri yükler,

02-playbookcheckpackages.yaml; loopta belirtilen paketlerin versiyon bilgilerini getirir (Aslında bunun hatalı bir değer döndürdüğünü farkettim, (yüklü olmayan bir paket varsa ve bu paket ismi loopta geçiyorsa hata alıyorum. Incelenecek;)

03-01intallmain.yaml; sırası ile diğer playbookları çağırıyor;

03-02,03,04,05 playbooklarını inceleyelim;

    03-02 playbook’u; mertdb isminde bir db oluşturacak,
    03-03 playbook’u; mertdb database için kullanıcı, şifre ve rol ataması gerçekleştirecek,
    03-04 playbook’u; yaratılan db ve detayları için pg_hba conf dosyasını dışarıdan erişilebilir hale getirecek (0.0.0.0/0 veya nereden erişmek istiyorsanız)
    03-05 playbook’u; postgresql servisini restart edecek,

04-01changelastsetting.yaml; 03-01intallmain.yaml dosyasında olduğu gibi sırası ile 2 playbook çalıştıracak, belirtilen playbookları inceleyelim;

    04-02 playbook’u; postgresql/13/main/postgresql.conf içerisinde listen_address’i * olarak değişiriyor,
    03-05 playbook’u; postgresql servisini restart edecek,

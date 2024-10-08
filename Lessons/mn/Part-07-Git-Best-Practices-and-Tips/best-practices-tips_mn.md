# Git зөв хэвшил болон зөвлөгөө

--

## Гарчиг

- [Commit түүхийг цэгцтэй байлгах](#commit-түүхийг-цэгцтэй-байлгах)
  - [Ойр ойрхон, утга учиртай commit хийх](#ойр-ойрхон,-утга-учиртай-commit-хийх)
  - [Дэлгэрэнгүй commit message өгөх](#дэлгэрэнгүй-commit-message-өгөх)
  - [Branch-г ухаалгаар ашиглах](#branch-г-ухаалгаар-ашиглах)
  - [Rebase хийж түүхийг цэгцтэй байлгах](#rebase-хийж-түүхийг-цэгцтэй-байлгах)
  - [Push хийхээс өмнө commit-уудыг squash болон засвар хийх](#push-хийхээс-өмнө-commit-уудыг-squash-болон-засвар-хийх)
  - [Main Branch руу шууд push хийхээс зайлсхийх](#main-branch-руу-шууд-push-хийхээс-зайлсхийх)
  - [Git Hooks ашиглах](#git-hooks-ашиглах)
  - [Өөрчлөлт шинэчлэлийг бүртгэх](#өөрчлөлт-шинэчлэлийг-бүртгэх)
  - [Тогтмол засвар, цэвэрлэгээ хийх](#тогтмол-засвар,-цэвэрлэгээ-хийх)
- [Git alias(өөр нэр), товчлол ашиглах](#git-aliasөөр-нэр,-товчлол-ашиглах)
  - [Git alias-г ойлгох](#git-alias-г-ойлгох)
  - [Git Alias-г ашиглах](#git-alias-г-ашиглах)
  - [Git Alias-г хуваалцах](#git-alias-г-хуваалцах)
  - [GitHub дээр git alias ашиглах](#github-дээр-git-alias-ашиглах)
- [.gitignore-оор файл болон хавтас орхигдуулах](#gitignore-оор-файл-болон-хавтас-орхигдуулах)
  - [.gitignore гэж юу вэ?](#gitignore-гэж-юу-вэ)
  - [.gitignore үүсгэх](#gitignore-үүсгэх)
  - [.gitignore-н бичилт](#gitignore-н-бичилт)
  - [.gitignore-т бүтэц, загвар ашиглах](#gitignore-т-бүтэц,-загвар-ашиглах)
  - [.gitignore жишээ](#gitignore-жишээ)
  - [Global .gitignore](#global-gitignore)
- [Хамтран ажиллах ажлын урсгал болон код хянах ёс зүй](#хамтран-ажиллах-ажлын-урсгал-болон-код-хянах-ёс-зүй)
  - [Git дэх хамтын ажлын урсгал](#git-дэх-хамтын-ажлын-урсгал)
  - [Код хянах ёс зүй](#код-хянах-ёс-зүй)
  - [Код хянах хэрэгслийг үр дүнтэй ашиглах](#код-хянах-хэрэгслийг-үр-дүнтэй-ашиглах)
  - [GitHub дээр хамтран ажиллах](#gitHub-дээр-хамтран-ажиллах)

---

## Commit түүхийг цэгцтэй байлгах

Git гэх мэт хувилбарын хяналтын системүүд болон GitHub зэрэг платформууд нь программ хангамжийн хөгжүүлэлтийг удирдах, хамтран ажиллах аргад хувьсгал хийсэн. Git болон GitHub-ийг үр дүнтэй ашиглах нэг чухал тал бол цэвэр, зохион байгуулалттай commit түүхийг хадгалах явдал юм. Сайн арчилгаатай commit түүх нь хөгжүүлэгчдэд төслийн хувьслыг илүү сайн ойлгоход тусалдаг төдийгүй debug хийх, кодыг хянах, хамтран ажиллахад тусалдаг. Энэ нийтлэлд бид Git болон GitHub-д commit түүхийг удирдах дадлага, арга техникийг судлах болно.

### Ойр ойрхон, утга учиртай commit хийх

Тогтмол бөгөөд утга учиртай commit нь цэгцтэй commit түүхийн үндэс суурь болдог. Олон тооны өөрчлөлтийг нэг том commit болгон нэгтгэхийн оронд ажлын логик нэгжүүдийг төлөөлөх жижиг commit хийгээрэй. Commit бүр нь нэг тодорхой асуудал, алдаа засах эсвэл функцийг шийдвэрлэх ёстой. Энэ арга нь илүү сайн ойлгоход тусалдаг төдийгүй шаардлагатай бол өөрчлөлтийг буцаахад хялбар болгодог.

### Дэлгэрэнгүй commit message өгөх

Сайн бичигдсэн commit мессеж нь commit-оор оруулсан өөрчлөлтийг ойлгоход маш чухал юм. "Алдаа засах" эсвэл "Кодыг шинэчлэх" гэх мэт ерөнхий мэдээллүүдээс зайлсхий. Харин өөрчлөлт, түүний цаад шалтгааныг тодорхой бөгөөд товч тайлбарлах хэрэгтэй. Commit мессеж нь команд эсвэл заавар шиг уншигдахуйц байх ёстой. Жишээлбэл:

Сайн: "Хэрэглэгчийн баталгаажуулалтын функцийг нэмэх"
Тохиромжгүй: "Зарим зүйл нэмж, зассан"

### Branch-г ухаалгаар ашиглах

Git дэх branch нь үндсэн кодын санд нөлөөлөхгүйгээр тусдаа функцууд дээр ажиллах эсвэл алдаа засах боломжийг олгодог хүчирхэг хэрэгсэл юм. Өөрийн ажиллаж буй шинэ функц, асуудал бүрт шинэ branch үүсгээрэй. Ингэснээр үндсэн branch (ихэвчлэн master эсвэл main) нь тогтвортой хэвээр байх бөгөөд төслийн суурь болгон ашиглаж болно. Branch-н ажил дуусч, шалгагдсаны дараа үүнийг цэвэр, сайн баримтжуулсан merge commit-оор үндсэн branch руу нэгтгэнэ.

### Rebase хийж түүхийг цэгцтэй байлгах

Git нь шулуун түүхийг хадгалахын зэрэгцээ нэг салбараас нөгөө салбар руу өөрчлөлт оруулах боломжийг олгодог "rebasing" хэмээх ашигтай функцээр хангадаг. Шаардлагагүй merge commit шинээр үүсгэдэг merge branch хийж нэгтгэхийн оронд git rebase ашиглан үндсэн branch-н өөрчлөлтүүдийг шинэ функцийн branch руу нэгтгэ. Rebase нь commit түүхийг цэгцтэй, ойлгоход хялбар байлгахад тусалдаг.

### Push хийхээс өмнө commit-уудыг squash болон засвар хийх

Өөрчлөлтөө GitHub гэх мэт дундын repository руу оруулахаасаа өмнө commit-уудаа squash хийж, засварлах замаар commit түүхийг цэвэрлэж болно. `git rebase -i`-г ашиглан branch-аа интерактив байдлаар дахин тохируулж, олон commit-уудыг нэг болгон нэгтгэж эсвэл тодорхой болгохын тулд commit мессежийг засаарай. Commit squash хийх нь эмх замбараагүй байдлыг багасгахаас гадна commit бүр нь утга учиртай, бүрэн өөрчлөлтийг илэрхийлэхэд тусалдаг.

### Main Branch руу шууд push хийхээс зайлсхийх

Хамтран ажиллах орчинд шууд үндсэн branch руу түлхэхээс зайлсхийх нь чухал. Үүний оронд GitHub гэх мэт платформ дээрх pull request ашиглан өөрчлөлтийг санал болгож, багийн гишүүдээр хянуул. Энэ нь шинэ кодыг үндсэн branch руу нэгтгэх илүү бүтэцтэй, зохион байгуулалттай хандлагыг бий болгож, үйл commit түүхийг цэгцтэй байлгах боломжийг олгодог.

### Git Hooks ашиглах

Git hooks нь Git-н урсгалын тодорхой цэгүүдэд өдөөгдөх боломжтой скриптүүд юм. Pre-commit hook-г ашиглаж commit message-н стандартыг хэрэгжүүлэх эсвэл pre-push hook ашиглаж кодыг remote repository руу push хийхээс өмнө тест явуул. Энэ нь тууштай байдлыг хадгалахад тусалдаг бөгөөд зөвхөн цэвэр, сайн туршсан өөрчлөлтүүдийг push хийж өгдөг.

### Өөрчлөлт шинэчлэлийг бүртгэх

Тодорхой commit message-ээс гадна төслийн өөрчлөлтийн бүртгэл эсвэл хувилбарын тэмдэглэл хөтлөх талаар бодож үзээрэй. Энэхүү баримт бичгийг repository-н README эсвэл тусгай файлд оруулж болно. Өөрчлөлтийн бүртгэл нь хувилбар бүрд оруулсан өөрчлөлтүүдийн тоймыг өгдөг бөгөөд энэ нь хамтран ажиллагсад болон хэрэглэгчдэд юу шинэ, юу засагдсаныг ойлгоход хялбар болгодог.

### Тогтмол засвар, цэвэрлэгээ хийх

Төсөл хөгжихийн хэрээр commit түүхийг тогтмол хянаж, цэвэрлэж байх цаг гарга. Шаардлагагүй эсвэл түр зуурын branch-г устгаж, нэгтгэсэн branch-г устгаж, хуучирсан эсвэл төөрөгдүүлсэн commit-уудыг rebase хийх, squash хийх талаар бодож үзээрэй.

Git болон GitHub дээрх цэгцтэй түүх нь зөв хэвшил төдийгүй программ хангамжийг үр дүнтэй хөгжүүлэх чухал хэсэг юм. Тогтмол commit хийж, дэлгэрэнгүй commit message бичиж, branch-г ухаалгаар ашиглаж, rebase, squash зэрэг Git-ийн хүчирхэг функцүүдийг ашиглан хөгжүүлэгчид зохион байгуулалттай, утга учиртай commit түүхийг хадгалж чадна. Нэмж дурдахад Git hook оруулах, өөрчлөлтийг баримтжуулах, байнгын засвар үйлчилгээ хийх нь төслийг хөгжүүлэлтийн туршид сайн бүтэцтэй, хамтын ажиллагаатай байлгахад тусалдаг.

## Git alias(өөр нэр), товчлол ашиглах

Git бол хөгжүүлэгчид эх кодыг удирдах, төсөл дээр хамтран ажиллахад өргөн хэрэглэгддэг хүчирхэг хувилбарын хяналтын систем юм. Git-ийн давуу талуудын нэг нь уян хатан байдал, өөрчлөн тохируулах чадвар бөгөөд энэ нь хэрэглэгчдэд байнга хэрэглэгддэг командуудад өөр нэр өгөх, товчлол үүсгэх боломжийг олгодог. Git alias болон товчлолууд нь бүтээмжийг эрс сайжруулж, бичилтийг багасгаж, Git командуудыг илүү ойлгомжтой болгодог. Энэ нийтлэлд бид Git болон GitHub-ын ажлын урсгалыг сайжруулахын тулд Git alias, товчлолыг хэрхэн тохируулах, ашиглах талаар судлах болно.

### Git alias-г ойлгох

Git alias нь Git командын тусгай товчлол юм. Эдгээр нь Git-ийн нарийн төвөгтэй эсвэл байнга хэрэглэгддэг үйлдлүүдэд зориулсан энгийн товчлол, бүр цоо шинэ командуудыг үүсгэх боломжийг олгодог. Git alias-г Git тохиргооны файлд (.gitconfig) тодорхойлох бөгөөд энэ нь таны эх хавтас (~/.gitconfig) эсвэл төслийн үндсэн хавтас (.git/config) дотор байрладаг. Та бүх repository-д хамаарах ерөнхий эсвэл тодорхой төсөлд хамаарах дотоод alias тохируулж болно.

Git alias үүсгэхийн тулд `git config` командыг ашиглах эсвэл .gitconfig файлыг шууд засварлаж болно.

Ерөнхий git alias үүсгэх:

Git config командыг ашиглан ерөнхий Git alias үүсгэхийн тулд терминалаа нээгээд дараахыг оруулна уу:

```
git config --global alias.alias_name 'original_command'

```

alias_name-г өөрийн хүссэн өөр нэрээр, original_command богиносгохыг хүссэн бүтэн Git командаар солино уу. Жишээлбэл, git status-д alias үүсгэхийн тулд:

```
git config --global alias.st status

```

Дотоод git alias үүсгэх:

Тодорхой төсөлд дотоод Git alias үүсгэхийн тулд терминал дээрх төслийн үндсэн хавтас руу очиж, --global сонголтгүйгээр өмнөх git config командыг ашиглана:

```
git config alias.alias_name 'original_command'

```

### Git Alias-г ашиглах

Та Git-н alias тохируулсны дараа шууд ашиглаж эхлэх боломжтой. Git үйлдлүүдийг ажиллуулахдаа бүтэн командын оронд зүгээр л alias-г бичнэ. Жишээлбэл, хэрэв та status-д st alias үүсгэсэн бол одоо дараахыг ашиглаж болно:

```
git st

```

Энэ нь танд git status-тай ижил үр дүнг өгөх болно.

#### Хэрэгтэй Git Alias-н жишээ:

Таны ажлын урсгалыг сайжруулж болох ашигтай Git alias-н зарим жишээ:

```
# Нийтлэг командуудын товчлол
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.br branch

# Commit түүхийг товчилсон байдлаар харуулах
git config --global alias.lg "log --oneline --decorate --all --graph"

# Өнгөлөг, илүү уншигдахуйц гаралтыг харуулах
git config --global alias.l "log --pretty=format:'%C(auto)%h %Cblue%ad %Creset%s%C(auto)%d %Cgreen[%an]' --date=short"

# Repository-н одоогийн статусыг харуулах
git config --global alias.s status

# Тодорхой файлын commit түүхийг харах
git config --global alias.filelog "log -u"

# Өөрчлөлтүүдийг устгалгүй сүүлчийн commit-г цуцлах
git config --global alias.undo "reset HEAD~1"

# Сүүлийн commit-г stage хийсэн өөрчлөлтөөр засах
git config --global alias.amend "commit --amend --no-edit"

```

Эдгээр нэрсийг өөрийн сонголт, ажлын урсгалд тохируулан өөрчилж болно.

### Git Alias-г хуваалцах

Хэрэв та багаар эсвэл олон машин дээр ажилладаг бол Git alias-аа хуваалцах нь ашигтай байх болно. Та өөрийн .gitconfig файлаас холбогдох оруулгуудыг багийнхаа найзууд болон бусад машинуудын .gitconfig файлууд руу хуулж alias-аа хуваалцаж болно. Эсвэл та git config командыг ашиглан тэдгээр машинууд дээр шууд өөр нэр тохируулах боломжтой.

To share your aliases with others, provide them with the following command:
Бусадтай alias-аа хуваалцахын тулд дараах командыг хуваалц:

```
git config --global alias.alias_name 'original_command'

```

### GitHub дээр git alias ашиглах

Git-н alias нь GitHub repository-той ямар ч саадгүй ажилладаг. Та GitHub repository clone хийх, push, pull эсэхээс үл хамааран Git-ийн стандарт командуудын нэгэн адил тодорхойлсон alias ашиглаж болно. Alias нь таны машин дээр дотоод байдлаар ашиглагдах бөгөөд GitHub дээр байрлуулсан remote repository-д нөлөөлөхгүй.

Git alias болон товчлол нь Git болон GitHub ашигладаг аливаа хөгжүүлэгчийн хувьд үнэ цэнтэй хэрэгсэл юм. Утгатай, ойлгомжтой alias тохируулснаар та бүтээмжээ мэдэгдэхүйц сайжруулж, Git командуудыг санах, ашиглахад хялбар болгох боломжтой. Та нийтлэг командын товчлол эсвэл нарийн төвөгтэй үйлдлүүдийн товчлолыг илүүд үздэг эсэхээс үл хамааран Git alias нь Git-ийн ажлын урсгалыг өөрийн хэрэгцээнд нийцүүлэн тохируулах боломжийг олгодог. Git alias үр дүнтэй ашиглаж, хуваалцсанаар та болон танай баг хөгжүүлэлтийн процессыг хялбарчилж, илүү үр дүнтэй хамтран ажиллах боломжтой.

## .gitignore-оор файл болон хавтас орхигдуулах

Программ хангамж хөгжүүлэхэд хувилбарын хяналт нь эх кодын өөрчлөлтийг удирдах, бусад хөгжүүлэгчидтэй үр дүнтэй хамтран ажиллахад зайлшгүй шаардлагатай. Хамгийн алдартай хувилбарын хяналтын системүүдийн нэг болох Git нь хөгжүүлэгчдэд өөрчлөлтийг хянах, салбар үүсгэх, кодыг саадгүй нэгтгэх боломжийг олгодог. Гэхдээ төслийн бүх файл, хавтсыг Git хянах ёсгүй. Жишээлбэл, build-аас үүссэн файлууд, түр зуурын файлууд болон нууц агуулсан файлыг ихэвчлэн хувилбарын хяналтаас гадуур орхидог. Үүнийг хэрэгжүүлэхийн тулд Git нь .gitignore файл гэсэн энгийн бөгөөд хүчирхэг шийдлийг санал болгодог. Энэ нийтлэлд бид .gitignore-г ашиглан зарим файл, лавлахыг Git-ээр хянах боломжгүй болгох талаар судлах болно.

### .gitignore гэж юу вэ?

.gitignore файл нь Git-д өөрчлөлт оруулах үед ямар файл, хавтсыг орхигдуулахыг заадаг энгийн текст файл юм. Таныг .gitignore жагсаалтад файл эсвэл хавтас нэмэх үед Git нь тэдгээрийг хянахаас хасах бөгөөд энэ нь тэдгээр файлууд нь staging хэсэгт харагдахгүй бөгөөд эдгээр файлд хийсэн өөрчлөлтүүд нь commit-д бүртгэгдэхгүй гэсэн үг юм.

### .gitignore үүсгэх

.gitignore-г ашиглаж эхлэхийн тулд Git repository-н эх хавтсанд .gitignore нэртэй файл үүсгэнэ үү. Та энэ файлыг үүсгэхийн тулд дурын текст засварлагч ашиглаж болно. Файлыг ямар ч өргөтгөлгүйгээр яг .gitignore гэж нэрлэх нь чухал.

Жишээ нь терминал ашиглан .gitignore файлыг ингэж үүсгэнэ:

```
touch .gitignore

```

### .gitignore-н бичилт

.gitignore файл нь аль файл, хавтсыг оруулахгүй орхихыг заах энгийн загвар ашигладаг. Бичилтийн үндсэн дүрэмд:

Хоосон мөр эсвэл #-ээр эхэлсэн мөрүүдийг тайлбар гэж үзэх бөгөөд Git үүнийг үл хэрэгсдэг.
Тодорхой файлыг орхигдуулахын тулд түүний нэрийг repository-н үндсэн хавтасны харьцангуй замын хамт бичнэ.
Хавтсыг орхигдуулахын тулд хавтасны нэрийг төгсгөлд нь ташуу зураастай (/) бичнэ.

### .gitignore-т бүтэц, загвар ашиглах

Та .gitignore-д янз бүрийн загвар ашиглаж олон файл эсвэл хавтас орхигдуулж болно. Зарим түгээмэл хэрэглэгддэг загварууд нь:

Оруулагч тэмдэгтүүд (_): Файл эсвэл хавтасны нэрийн хэдэн ч тэмдэгттэй тохирно. Жишээлбэл, _.log нь бүх .log файлуудыг орхигдуулах ба build/\*/ нь build нэртэй бүх хавтсыг орхишдуулна.

Оруулагч тэмдэгтүүд(\*\*): Хавтасны аль ч түвшний дэд хавтастай таарна. Жишээлбэл, logs/\*\*/\*.log нь log-н аль ч дэд хавтас дахь бүх .log файлыг орхигдуулдаг.

Үгүйсгэх (!): Өмнөх орхигдуулах дүрмийг буцаана. Жишээлбэл, хэрэв та бүх .txt файлыг орхигдуулж, нэгийг нь үлдээхийг хүсвэл бүх .txt файлыг орхигдуулахын тулд \*.txt, дараа нь !important.txt ашиглан important.txt файлыг оруулах боломжтой.

### .gitignore жишээ

Here are some common examples of .gitignore entries:
.gitignore бичилтийн зарим нийтлэг жишээ:

```
# Build-аас үүссэн файл, хавтсыг орхигдуулах
build/
dist/
bin/

# log файлуудыг орхигдуулах
*.log

# Түр зуурын файлуудыг орхигдуулах
*.tmp
*.temp

# Тохиргоо, нууцлалын файлуудыг орхигдуулах
config.ini
secrets.json

# Тодорхой хавтас орхигдуулах
data/*

# Тодорхой өргөтгөлтэй файлуудыг орхигдуулах
*.exe
*.dll


```

.gitignore нь зөвхөн git-д ороогүй файлуудад хамаарна гэдгийг санаарай. Хэрэв та файлыг .gitignore-д нэмэхээсээ өмнө git-д оруулсан бол түүнийг үргэлжлүүлэн хянах болно.

### Global .gitignore

Заримдаа танд олон Git repository дунд нийтлэг орхигдуулах хэв загвар байж болно. Repository бүрд тусад нь .gitignore файл үүсгэхийн оронд та бүх repository-г хамрах global .gitignore тохируулж болно.

Үүнийг хийхийн тулд өөрийн үндсэн хавтсанд global .gitignore файл үүсгээд Git-д үүнийг бүх repository-д ашиглахыг зааж өгөөрэй. Эдгээр алхмуудыг дагана уу:

Global .gitignore файл үүсгэх:

```
touch ~/.gitignore_global

```

Энгийн .gitignore файлтай ижил бичилт ашиглан орхигдуулах хэв загвараа global файл нэмнэ.

Git-д global .gitgnore файлыг ашиглахыг заах:

```
git config --global core.excludesfile ~/.gitignore_global

```

.gitignore ашиглах нь Git repository-г үр дүнтэй удирдах суурь юм. Хянаж болохгүй файлууд болон хавтсыг орхигдуулснаар та repository-оо цэвэр байлгаж, хувилбарын түүхээ хамааралгүй өөрчлөлтүүдээр дүүргэхээс сэргийлж, нууц мэдээллийг санамсаргүй байдлаар оруулахаас сэргийлж чадна. .gitignore файл нь ямар файл, хавтас оруулахгүй байхыг зааж өгөх хүчирхэг хэрэгсэл бөгөөд хэв загвартай тааруулах энгийн дүрмүүдийг ашиглана. Та шинэ төсөл дээр ажиллаж байгаа эсвэл багаар хамтран ажиллаж байгаа эсэхээс үл хамааран .gitignore-ийн хэрэглээг эзэмшсэнээр таны Git-н урсгалыг сайжруулж, илүү зохион байгуулалттай, үр дүнтэй хөгжүүлэлтийн үйл явцад хувь нэмэр оруулах нь дамжиггүй.

## Хамтран ажиллах ажлын урсгал болон код хянах ёс зүй

Орчин үеийн программ хангамж хөгжүүлэлтийн гол цөм нь хамтын ажиллагаа байдаг бөгөөд Git зэрэг хувилбар хяналтын системүүд болон GitHub зэрэг платформууд хөгжүүлэгчдийн хамтын ажиллагааг эрс шинэчилсэн. Хамтын ажиллагааны үр дүнтэй урсгалууд болон код хянах ёс зүй нь өндөр чанартай кодын санг хадгалах, багийн эерэг соёлыг бий болгох, шинэ функц болон алдаа засваруудыг тасралтгүй нэгтгэхэд маш чухал ач холбогдолтой. Энэхүү нийтлэлд бид Git болон GitHub дээрх хамтын ажиллагааны урсгалууд болон код хянах ёс зүйн гол элементүүдийг судлах болно.

### Git дэх хамтын ажлын урсгал

Git нь хэд хэдэн хамтын ажиллагааны урсгалыг санал болгодог бөгөөд хамгийн түгээмэл хоёр нь Төвлөрсөн урсгал (Centralized Workflow) болон Функцийн branch урсгал (Feature Branch Workflow) юм.

Төвлөрсөн урсгал:
Төвлөрсөн урсгалд багийн бүх гишүүд нэг салбар дээр, ихэвчлэн main эсвэл master салбар дээр шууд ажилладаг. Хөгжүүлэгчид repository-г clone хийгээд өөрийн компьютер дээр өөрчлөлтүүдийг хийж, хийсэн ажлаа төв repository руу push хийдэг. Энэ арга барил нь маш энгийн бөгөөд жижиг төслүүд эсвэл бага өөрчлөлт оруулдаг төслүүдэд тохиромжтой.

Гэвч энэ төвлөрсөн урсгал нь шинэ функцийн хөгжүүлэлтийг тусгаарлаж чаддаггүй тул зөрчилдөөн үүсгэж, параллель хөгжүүлэлтийг хязгаарладаг.

Функцийн branch урсгал:
Функцийн branch урсгал нь том төсөл болон багт тохиромжтой. Энэ ажлын урсгалд шинэ функц эсвэл алдаа засвар бүрийг өөрийн гэсэн branch дээр хөгжүүлэлдэг. Хөгжүүлэгчид тодорхой ажилд зориулж шинэ branch үүсгэн, засварууд дээр ажиллаж, дууссаны дараа branch-г үндсэн branch-д нэгтгэдэг.

Функцийн branch урсгал нь шинэ функцийн хөгжүүлэлтийг тусгаарлаж, зөрчилдөөнийг багасгаж код хяналтыг хялбаршуулдаг. Энэ нь хөгжүүлэгчдэд бие даан ажиллах боломжийг олгож шинэ кодыг main branch-тай нэгтгэх үйл явцыг хялбаршуулна.

### Код хянах ёс зүй

Код хяналт бол хамтын хөгжүүлэлтийн салшгүй хэсэг юм. Энэ нь алдааг эрт олох, кодын чанарыг сайжруулах болон зөв хэвшлийг мөрдөхөд хэрэгтэй. Код хяналтын ёс зүйн зарим чухал зөвлөмжүүдийг хүргэж байна:

Хүндлэлтэй байж, үр дүнг чухалчил:
Код хяналт нь тухайн хөгжүүлэгчийг шүүмжлэхэд бус, кодыг сайжруулахад чиглэсэн гэдгийг санаарай. Санаа бодлоо хүндэтгэлтэй, бүтээлч байдлаар илэрхийл. Хувийн сонирхлоос илүү кодын чанар, стандарт болон ерөнхий дизайнд анхаарлаа хандуул.

Агуулгыг ойлгох:
Санал бодлоо өгөхөөсөө өмнө өөрчлөлтийн агуулгыг ойлгохыг хичээгээрэй. Тухайн функц эсвэл засварын зорилго, мөн холбогдох дизайны шийдэл, хязгаарлалттай танилцаарай.

### Код хянах хэрэгслийг үр дүнтэй ашиглах:

Github болон бусад платформууд дээрх код хяналтын хэрэгслүүдийг ашигла. Мөр хоорондын "comment" ашиглаж тодорхой асуудлыг тэмдэглэх болон сайжруулалт санал болгоорой. Хэт том, дарамттай comment-оос зайлсхийж, харин тэдгээрийг жижиг, хэрэгжүүлэхэд хялбар болгон хувааж өгөөрэй.

Дээд болон доод түвшний асуудлын аль алиныг авч үз:
Ерөнхий архитектур, дизайн загварууд, кодын зохион байгуулалт зэрэг өндөр түвшний асуудал болон хувьсагчийн нэрс, кодын формат, алдааны боловсруулалт зэрэг доод түвшний дэлгэрэнгүй мэдээллүүдэд аль алинд нь санал бодлоо илэрхийлээрэй. Эдгээр талуудад анхаарал хандуулах нь илүү цогц кодын шалгалт хийхэд хувь нэмэр оруулдаг.

Жижиг зүйлс дээр хэт төвлөрөхөөс зайлсхий:
Нарийвчлалтай хандах нь чухал боловч кодын үйл ажиллагаа, засвар хөгжүүлэлт зэрэгт нөлөөлөхгүй жижиг асуудлууд дээр хэт төвлөрөхөөс зайлсхийх хэрэгтэй.

Хугацааны талаар бодитой хүлээлт тогтоо:
Өөрчлөлтийн яаралтай байдлыг харгалзан үзэж, код хяналтдаа бодитой цаг хугацаа хуваарил. Жижиг, чухал бус өөрчлөлтүүд хурдан эргэлттэй байдаг бол томоохон өөрчлөлт эсвэл шинэ функционалийн нэвтрүүлэлт илүү цаг хугацаа шаарддаг.

Санал бодол хүлээж авахад бэлэн бай:
Кодын зохиогчийн хувьд санал гомдол хүлээн авахад бэлэн байгаарай. Санал гомдлыг өсөж дэвших боломж гэж үзэж хянагчаас ирсэн асуудлыг шийдвэрлэхэд бэлэн бай.

Автоматжуулсан хяналт шалгалтыг ашигла:
Код хяналт хийж эхлэхээс өмнө автоматжуулсан хяналт шалгалт явуулж кодын загварын зөрчил анхан шатны алдаа зэрэг нийтлэг асуудлыг илрүүлэх хэрэгтэй. Ингэснээр хянагчид өндөр түвшний асуудал дээр төвлөрөх боломжийг хангана.

### GitHub дээр хамтран ажиллах

GitHub нь Git-н ажлын урсгалыг дэмжих олон хамтын ажиллагааны функцүүдийг санал болгодог. Хамтын хөгжүүлэлтэд зориулсан зарим функцүүдэд:

#### Pull Requests:

Pull Request (PR) нь функцийн branch урсгалын гол тулгуур юм. Хөгжүүлэгчид өөрийн функцийн branch-ыг main branch-д нэгтгэхэд бэлэн болсон үедээ pull request үүсгэдэг. PR-ууд нь өөрчлөлтийн тодорхой тоймыг өгч, багийн гишүүдэд кодыг merge хийхээс өмнө сэтгэгдэл үлдээх, санал болгох, кодыг хэлэлцэх боломжийг олгосноор кодын шалгалтыг хөнгөвчилдөг.

#### Код хянах хүсэлт:

Pull request үүсгэх үедээ тодорхой багийн гишүүдээс өөрчлөлтийг шалгахыг хүсээрэй. Ингэснээр зөв хүн нь мэдэгдэл авч, хяналтын явц үр дүнтэй болно.

#### Статус шалгалт болон Continuous Integration (CI):

Шинэ pull request үүсэхэд автомат туршилтууд болон шалгалтуудыг ажиллуулахын тулд статус шалгалт болон CI-г тохируулаарай. Энэ нь кодыг main branch-д нэгтгэхээс өмнө нэмэлт итгэл олгодог.

#### Label болон Milestone(Чухал Үе Шат):

Pull request-уудыг ангилах, хянахын тулд label болон milestone-г ашиглаарай. Label нь PR-ийн төлөвийг (жишээ нь, "шалгах шаардлагатай," "ажил үргэлжилж байна") илтгэж, milestone нь тодорхой хувилбар эсвэл функцэд хамаарах PR-уудыг нэгтгэн зохион байгуулж болно.

Хамтын ажлын урсгалууд болон кодын шалгалтын ёс зүй нь Git болон GitHub-ийг ашиглах амжилттай программ хангамжийн хөгжүүлэлтийн үндсэн элементүүд юм. Таны багт тохирсон ажлын урсгалыг, жишээлбэл Функцийн Branch Ажлын Урсгалыг нэвтрүүлснээр зэрэгцээ хөгжүүлэлтийг илүү жигд явуулах, мөргөлдөөнийг багасгах боломжтой. Баримжаатай санал шүүмж, агуулгыг ойлгох, кодын шалгалтын хэрэгслүүдийг үр дүнтэй ашиглах зэрэг кодын шалгалтын ёс зүй нь багийн эерэг соёл төлөвшүүлж, кодын чанарыг сайжруулдаг. GitHub-ийн хамтын ажиллагааны функцүүдийг, тухайлбал pull request, статус шалгалт, milestone зэргийг ашигласнаар хөгжүүлэлтийн үйл явц жигдэрч, багийн хамтын ажиллагаа нэмэгдэнэ. Эдгээр туршлагуудыг ажлын урсгалдаа нэгтгэснээр илүү зохион байгуулалттай, үр дүнтэй, хамтын ажиллагаатай программ хангамжийн хөгжүүлэлтийн үйл явцад хүрэх боломжтой.

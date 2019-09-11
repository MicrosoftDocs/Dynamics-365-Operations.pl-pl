---
title: Dwuwalutowość
description: Ten temat zawiera informacje o dwuwalutowości, gdzie waluta raportowania służy jako druga waluta rozliczeniowa w programie Microsoft Dynamics 365 for Finance and Operations.
author: kweekley
manager: AnnBe
ms.date: 08/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, Ledger, AssetTransReportingCurrencyAmountsWizard,BankAccountTransReportingCurrencyAmountsWizard, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.search.scope: ''
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 6d5128ea9daaf22ee962ca5fc70a05cba05c7edb
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867518"
---
# <a name="dual-currency"></a>Dwie waluty

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Funkcjonalność wprowadzona w programie Microsoft Dynamics 365 for Finance and Operations w wersji 8.1 (w październiku 2018 r.) umożliwia zmianę przeznaczenia waluty raportowania i używanie jej jako drugiej waluty rozliczeniowej. Ta funkcja jest nazywana *dwuwalutowością*. Zmian ustawień dwuwalutowości nie można wyłączyć za pomocą klucza konfiguracji lub parametru. Ponieważ waluta raportowania jest używana jako druga waluta rozliczeniowa, zmieniono sposób obliczana waluty raportowania w logice księgowania.

Ponadto zmodyfikowano kilka modułów, tak aby śledziły, raportowały i wykorzystywały walutę raportowania w różnych procesach. Dotyczy to następujących modułów:

- Księga główna 
- Raportowanie finansowe 
- Rozrachunki z dostawcami
- Rozrachunki z odbiorcami 
- Zarządzanie gotówką i bankami 
- Środki trwałe 
- Konsolidacje

Po uaktualnieniu należy wykonać określone czynności w modułach Zarządzanie gotówką i bankami oraz Środki trwałe. W związku z tym należy uważnie przeczytać i zrozumieć odpowiednie sekcje tego tematu.

## <a name="posting-process"></a>Proces księgowania

Zmieniono logikę księgowania dla wszystkich transakcji, które generują wpis księgowania w księdze głównej. Poniżej przedstawiono wcześniejszy sposób obliczania waluty raportowania:

Kwota w walucie transakcji \> Kwota w walucie rozliczeniowej \> Kwota w walucie raportowania

Na przykład wprowadzono transakcję w walucie Dolar kanadyjski (CAD). Kwota w CAD jest przeliczana na walutę rozliczeniową, którą jest dolar amerykański (USD). Kwota w USD jest następnie przeliczana na walutę raportowania, którą jest euro (EUR). Z tego względu muszą istnieć kursy wymiany między CAD i USD oraz między USD i EUR.

Oto nowy sposób obliczania:

Kwota w walucie transakcji \> Kwota w walucie rozliczeniowej

Kwota w walucie transakcji \> Kwota w walucie raportowania

Z powodu tej zmiany teraz muszą istnieć kursy wymiany między CAD i USD oraz między CAD i EUR.

## <a name="reports-and-inquiries"></a>Raporty i zapytania

Różne raporty i zapytania teraz zawierają zarówno kwoty w walucie raportowania, jak i kwoty w walucie rozliczeniowej. Nie wszystkie raporty i zapytania zostały zaktualizowane. Na przykład nie zostały zmienione raporty pokazujące kwoty tylko w walucie transakcji.

Zmian dokonano według jednego z dwóch wzorców:

- Jeśli raport lub zapytanie miało wystarczająco dużo miejsca, aby wyświetlić kwoty w walutach rozliczeniowej i raportowania, kwoty w walucie raportowania zostały dodane.
- Jeśli raport lub zapytanie nie miało wystarczająco dużo miejsca, aby wyświetlić kwoty w obu walutach, dodano opcję pozwalającą użytkownikom wybierać walutę do wyświetlenia.

W różnych raportach i zapytaniach dodano również logikę wyłączającą kwoty w walucie raportowania, jeśli waluta raportowania jest taka sama, jak waluta rozliczeniowa, albo jeśli waluta raportowania nie została zdefiniowana w księdze dla firmy.

## <a name="financial-journals"></a>Arkusze finansowe

Arkusze finansowe, takie jak arkusz finansowy i arkusz faktur od dostawców, zostały zaktualizowane, aby zawierały dodatkowe informacje o walucie raportowania. Sumy załączników i arkuszy są teraz wyświetlane w walucie raportowania. Ponadto informacje o kursie wymiany waluty raportowania są teraz wyświetlane na karcie **Ogólne** w wierszach arkusza. Z tego względu podczas wprowadzania transakcji można zastąpić kurs wymiany waluty raportowania.

## <a name="vendor-invoices-sales-orders-and-sales-agreements"></a>Faktury dostawcy, zamówienia sprzedaży i umowy sprzedaży
Faktury dostawcy, zamówienia sprzedaży i umowy sprzedaży zostały zaktualizowane, tak aby zawierały stały kurs wymiany dla waluty raportowania. Stały kurs wymiany można zdefiniować dla waluty rozliczeniowej i waluty raportowania w przypadku, gdy waluta transakcji jest inna. Jeśli waluta rozliczeniowa i waluta raportowania są takie same, stały kurs wymiany będzie zsynchronizowany przy użyciu stałej stawki waluty rozliczeniowej jako stałej stawki waluty raportowania. Nie można zmienić stałego kursu wymiany waluty raportowania dla tej konfiguracji. Gdy waluta rozliczeniowa jest inna niż waluta raportowania, stały kurs wymiany można zdefiniować dla waluty rozliczeniowej i waluty raportowania podczas wprowadzania transakcji. Jeśli waluta raportowania nie została zdefiniowana w księdze, pole **stały kurs wymiany waluty raportowania** nie jest włączone i nie jest obliczana żadna kwota w walucie raportowania.

## <a name="module-changes"></a>Zmiany w modułach

Następujące moduły używają waluty raportowania jako drugiej waluty rozliczeniowej:

- [Księga główna](#general-ledger)
- [Raporty finansowe](#financial-reporting)
- [Rozrachunki z dostawcami](#accounts-payable-and-accounts-receivable)
- [Rozrachunki z odbiorcami](#accounts-payable-and-accounts-receivable)
- [Zarządzanie gotówką i bankami](#cash-and-bank-management)
- [Środki trwałe](#fixed-assets)
- [Konsolidacje](#consolidations)

### <a name="general-ledger"></a>Księga główna

Jeśli zdefiniowano walutę raportowania w księdze, księga główna już śledziła kwoty w walucie raportowania w każdym wpisie księgowania. Jednak te kwoty teraz są przeliczane z kwot w walucie transakcji.

Następujące dodatkowe zmiany wprowadzono w module **Księga główna**:

- W księdze można zdefiniować osobny typ kursu wymiany dla waluty raportowania. Jeśli organizacja nie chce używać innego typu kursu wymiany, można nie wypełniać pola typu kursu wymiany dla waluty raportowania. Alternatywnie można wybrać ten sam typ kursu wymiany, jak używany dla waluty rozliczeniowej. Jeśli pole pozostanie puste, system będzie używał typu kursu wymiany waluty rozliczeniowej.
- Nowy arkusz — arkusz korekt w walucie raportowania — umożliwia księgowanie korekt na kontach księgowych tylko w walucie raportowania. Ten arkusz umożliwia księgowanie tylko na kontach księgowych. Nie obsługuje transakcji międzyfirmowych, a waluta musi być walutą raportowania firmy, w której arkusz jest księgowany. Podczas księgowania arkusza kwoty w walutach transakcji i rozliczeniowej są równe 0 (zero), a kwota w walucie raportowania jest księgowana z wartością wprowadzaną w transakcji. Ponieważ zmienił się sposób używania waluty raportowania w modułach **Rozrachunki z dostawcami**, **Rozrachunki z odbiorcami** i **Środki trwałe**, ten arkusz może służyć do wprowadzania korekt po uaktualnieniu. Przykłady, które pokazują, jak można używać tego arkusza, znajdują się w sekcjach dotyczących tych modułów.
- Proces alokacji okresów został zaktualizowany, tak że teraz przydziela kwoty w walutach transakcji, rozliczeniowej i raportowania. Wcześniej kwoty były przydzielane w walutach transakcji i rozliczeniowej, a następnie kwota w walucie rozliczeniowej była przeliczana na walutę raportowania. To zachowanie mogło powodować pozostawanie salda na koncie księgowym w walucie raportowania. Teraz gdy kwoty są obliczane i używane we wpisie księgowania, nie odbywa się przeliczanie.
- Proces przeszacowania w walucie obcej już przeszacował kwoty w walucie raportowania. Jednak kwota w walucie raportowania jest teraz obliczana przy użyciu kwoty w walucie transakcji, jak opisano w sekcji [Proces księgowania](#posting-process) wcześniej w tym temacie.
- Wiele raportów i zapytań w księdze głównej już zawierało walutę raportowania, ale niektóre nie. Jednym z przykładów jest strona listy **Bilans próbny**. Ta strona listy teraz zawiera kolumny zarówno dla waluty rozliczeniowej, jak i waluty raportowania. Należy zauważyć, że kolumny waluty raportowania są ukryte, jeśli waluta rozliczeniowa i waluta raportowania są takie same albo jeśli w księdze nie zdefiniowano waluty raportowania.

### <a name="financial-reporting"></a>Raportowanie finansowe

Ulepszenie modułu **Raportowanie finansowe** pozwala umieszczać kwoty w walucie raportowania w sprawozdaniu finansowym na dwa sposoby. W definicji kolumny można podawać bezpośrednio kwoty w walucie raportowania zaksięgowane w księdze (nowa funkcja). Alternatywnie można nadal przeliczać kwoty z waluty rozliczeniowej na walutę raportowania (istniejąca funkcja).

Ta zmiana jest dostępna za pośrednictwem ustawienia **Opcja wyświetlania waluty** w definicji kolumny. W przypadku wybrania opcji **Waluta raportowania z księgi** kwoty w kolumnie nie są przeliczane. Zamiast tego są podawane bezpośrednio z księgi głównej. Jeśli w kolumnie mają być wyświetlane kwoty przeliczone, zaznacz opcję **Przelicz na XXXX**, gdzie *XXXX* jest walutą raportowania, która ma być pokazywana w kolumnie. W takim wypadku kwoty w walucie rozliczeniowej zostaną przeliczone na wybraną walutę przy użyciu istniejących funkcji przeliczania.

### <a name="accounts-payable-and-accounts-receivable"></a>Rozrachunki z dostawcami/Rozrachunki z odbiorcami

Moduły **Rozrachunki z dostawcami** i **Rozrachunki z odbiorcami** już śledziły kwoty w walucie raportowania. Jednak te kwoty nie były wyświetlane ani używane w różnych procesach. Wprowadzono następujące zmiany:

- Kwoty w walucie raportowania są teraz wyświetlane w transakcjach z odbiorcami i dostawcami. Kwoty w walucie raportowania są także wyświetlane dla sald otwarcia każdej transakcji.
- Zaktualizowano proces wiekowania, tak aby organizacja mogła wyświetlać przedziały wiekowania w walucie rozliczeniowej lub walucie raportowania.
- Zaktualizowano różne raporty i zapytania, tak aby pokazywały kwoty w walucie raportowania. Dotyczy to na przykład raportów **Uzgadnianie odbiorca/księga** i **Uzgodnienie dostawca/księga**.
- Proces przeszacowania w walucie obcej już przeszacował kwoty w walucie raportowania. Jednak kwota w walucie raportowania jest teraz obliczana przy użyciu kwoty w walucie transakcji, jak opisano w sekcji [Proces księgowania](#posting-process).
- **Uwaga dotycząca uaktualnienia:** Przed uaktualnieniem kwoty w walucie raportowania dla dokumentów (faktur, płatności itd.) są obliczane przy użyciu waluty rozliczeniowej. Na przykład faktura została zaksięgowana przed uaktualnieniem w organizacji, a faktura nie jest zapłacona. Podczas uaktualniania wpis księgowania faktury nie ulega zmianie. Jednak po uaktualnieniu zaczynają obowiązywać zmiany wynikające z dwuwalutowości. W związku z tym podczas dokonywania zapłaty za fakturę kwota płatności w walucie raportowania jest teraz obliczana przy użyciu kwoty w walucie transakcji. Podczas rozliczania płatności i faktury może zostać obliczona niewielka różnica w kwocie zrealizowanej dodatniej/ujemnej różnicy kursowej, ponieważ kwoty w walucie raportowania są teraz obliczane w inny sposób. Jeśli obliczona różnica zostanie uznana za istotną, można użyć nowego arkusza korekt w walucie raportowania do skorygowania salda zrealizowanej dodatniej/ujemnej różnicy kursowej i stanów kont księgowych w module Rozrachunki z dostawcami/Rozrachunki z odbiorcami tylko w walucie raportowania.

### <a name="cash-and-bank-management"></a>Zarządzanie gotówką i bankami

Dawniej moduł **Zarządzanie gotówką i bankami** nie śledził żadnych kwot w walucie raportowania dla transakcji księgowanych na poszczególnych kontach bankowych. Po uaktualnieniu kwoty w walucie raportowania są śledzone automatycznie dla każdej nowo księgowanej transakcji. Jednak kwoty w walucie raportowania należy dodać do wcześniej zaksięgowanych transakcji w księgi podrzędnej.

- **Uwaga dotycząca uaktualnienia:** Ponieważ transakcje na kontach bankowych wcześniej nie śledziły kwot w walucie raportowania w księgi podrzędnej, dodano kreatora umożliwiającego dodawanie kwot w walucie raportowania do transakcji na kontach bankowych. Ten kreator **nie** księguje ponownie w księdze głównej. Zamiast tego pobiera kwoty w walucie raportowania z księgi głównej i aktualizuje je w tabelach księgi podrzędnej.

    - Aby uruchomić kreatora, wybierz kolejno opcje **Zarządzanie gotówką i bankami** \> **Ustawienia** \> **Dodawanie kwot w walucie raportowania do transakcji na kontach bankowych**.
    - Kreator pokazuje transakcje dla wszystkich kont bankowych w bieżącej firmie, które mają kwoty w walucie raportowania równe 0 (zero). Uwzględniane są tylko transakcje zaksięgowane przed uaktualnieniem.
    - Dla każdej transakcji na koncie bankowym kreator znajduje odpowiednie wpisy księgowania w księdze głównej i wprowadza domyślną kwotę w walucie raportowania. Mimo że te kwoty można edytować, zalecamy, aby tego **nie** robić. W przeciwnym razie mogą być problemy z uzgodnieniem sald kont bankowych z księgą główną. Jedyną sytuacją, gdy należy edytować kwotę, jest przypadek, gdy kwoty w walucie raportowania nie można odnaleźć w księdze głównej. Wtedy kreator wyświetli kwotę w walucie raportowania równą 0 (zero).
    - Jeśli w kreatorze wybierzesz opcję **Anuluj**, transakcje na kontach bankowych oraz wszelkie zmiany kwot w walucie raportowania zostaną zapisane do czasu ponownego uruchomienia kreatora. Jednak kwoty w walucie raportowania nie zostaną zaktualizowane w transakcjach na kontach bankowych. Ta aktualizacja następuje tylko po wybraniu opcji **Zakończ** w kreatorze. Kreatora można uruchamiać wiele razy. W związku z tym w razie pomyłki można skorygować każdą błędną kwotę w walucie raportowania.

- Nie zmieniono żadnych procesów w module Zarządzanie gotówką i bankami, ale zaktualizowano różne raporty i zapytania, tak aby pokazywały kwoty w walucie raportowania. Wyjątkiem są raporty z prognozowania przepływów pieniężnych. Nie zostały zaktualizowane w celu dodania kwot w walucie raportowania.

### <a name="fixed-assets"></a>Środki trwałe

Dawniej moduł **Środki trwałe** nie śledził żadnych kwot w walucie raportowania dla transakcji księgowanych w poszczególnych księgach środków trwałych. Po uaktualnieniu kwoty w walucie raportowania są śledzone automatycznie dla każdej nowo księgowanej transakcji. Jednak kwoty w walucie raportowania należy dodać do wcześniej zaksięgowanych transakcji w księgi podrzędnej.

Ponadto wprowadzono znaczne zmiany w procesie amortyzacji. Te zmiany wymagają działań ze strony użytkownika po uaktualnieniu. Ważne jest, aby przeczytać i zrozumieć zmiany opisane poniżej, nawet jeśli jeszcze nie używasz modułu Środki trwałe.

- Zmienił się sposób określania kwoty w walucie raportowania w procesie amortyzacji. W poniższym scenariuszu porównano sposób ustalania kwoty w walucie raportowania w procesie amortyzacji poprzednio i obecnie.



    **Scenariusz amortyzacji**

    Składnik aktywów został nabyty i zaksięgowany z następującymi kwotami. Należy zauważyć, że kwota w walucie raportowania jest księgowana w księdze głównej, ale nie jest zapisywana w tabelach podrzędnej księgi środków trwałych.

    | Typ transakcji | Kwota transakcji | Kurs wymiany | Kwota w walucie rozliczeniowej | Kurs wymiany | Kwota w walucie raportowania |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Nabycie      | 1 000 000 DKK      | 2.0           | 500 000 USD                | 2,5           | 200 000 EUR               |

    **Waluta raportowania w poprzednim procesie amortyzacji**

    Na koniec roku jest uruchamiany proces generowania propozycji amortyzacji i oblicza on następujące kwoty.

    | Typ transakcji | Kwota transakcji | Kurs wymiany | Kwota w walucie rozliczeniowej | Kurs wymiany | Kwota w walucie raportowania |
    |------------------|--------------------|---------------|----------------------------|---------------|---------------------------|
    | Amortyzacja     | 50 000 USD         | 1,0           | 50 000 USD                 | 2,6           | 19 230,77 EUR             |

    Po uruchomieniu procesu generowania propozycji amortyzacji oblicza on kwotę w walucie rozliczeniowej przy użyciu metody amortyzacji. Następnie przelicza tę kwotę na walutę raportowania przy użyciu bieżącego kursu wymiany między USD a EUR. To przeliczenie powoduje problemy, ponieważ składnika aktywów nie może w pełni zamortyzować w walucie raportowania, gdy jest używany kurs kasowy.

    **Waluta raportowania w nowym procesie amortyzacji**

    Proces amortyzacji został zmieniony tak, aby kwota w walucie raportowania była również obliczana przy użyciu metody amortyzacji. Poniżej przedstawiono wyniki zastosowania amortyzacji do składnika aktywów.

    | Typ transakcji | Kwota transakcji | Kurs wymiany | Kwota w walucie rozliczeniowej | Kurs wymiany                                                       | Kwota w walucie raportowania |
    |------------------|--------------------|---------------|----------------------------|---------------------------------------------------------------------|---------------------------|
    | Amortyzacja     | 50 000 USD         | 1,0           | 50 000 USD                 | 2,5<blockquote>[!NOTE] Chociaż ten kurs wymiany jest widoczny, nie jest używany do przeliczania na walutę raportowania.</blockquote> | 20 000 EUR                |

    Po uruchomieniu procesu generowania propozycji amortyzacji liczy on zarówno kwotę w walucie rozliczeniowej, jak i kwotę w walucie raportowania przy użyciu metody amortyzacji. Kwoty są następnie używane we wpisie księgowania w księdze głównej. Nie jest wykonywane przeliczenie w celu określenia kwoty w walucie raportowania.

- **Uwaga dotycząca uaktualnienia:** Ponieważ transakcje na księdze środków trwałych wcześniej nie śledziły waluty raportowania, dodano kreatora umożliwiającego dodawanie kwot w walucie raportowania do transakcji na księdze środków trwałych. Ten kreator **nie** księguje ponownie w księdze głównej. Ponieważ zmienił się sposób obliczania kwot w walucie raportowania w procesie generowania propozycji amortyzacji, kreatora **należy koniecznie** uruchomić i sfinalizować dla każdej firmy, zanim organizacja będzie mogła wprowadzać jakiekolwiek transakcje amortyzacji.

    - Aby uruchomić kreatora, wybierz kolejno opcje **Środki trwałe** \> **Ustawienia** \> **Dodawanie kwot w walucie raportowania do ksiąg środków trwałych**.
    - Kreator pokazuje transakcje dla wszystkich ksiąg środków trwałych w bieżącej firmie, które mają kwoty w walucie raportowania równe 0 (zero). Uwzględniane są tylko transakcje zaksięgowane przed uaktualnieniem.
    - Kreator **nie** pobiera kwot w walucie raportowania z księgi głównej. Jak opisano w poprzednim scenariuszu, kwoty w walucie raportowania, które zostały pierwotnie zaksięgowane w księdze głównej, błędnie używały kursu kasowego. Kwoty te nie powinny być widoczne w księdze podrzędnej środków trwałych, ponieważ wtedy w kolejnym obliczaniu amortyzacji byłyby używane niepoprawne wartości. Zamiast tego kreator znajduje kurs wymiany z dnia pierwszego nabycia. Następnie używa tego kursu wymiany do zarekomendowania kwoty w walucie raportowania, która powinna zostać księgowana w księgi podrzędnej. Na przykład oto co kreator może pokazywać w poprzednim scenariuszu.

        | Środek trwały | Rezerwowanie      | Typ transakcji | Data transakcji | Waluta | Kwota w walucie transakcji | Ilość  | Kurs wymiany | Kwota w walucie raportowania |
        |-------------|-----------|------------------|------------------|----------|--------------------------------|---------|-----------|---------------------------|
        | BUIL-00001  | 200\_SLLT | Nabycie      | 6/3/2016         | DKK      | 1 000 000                      | 500,000 | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Amortyzacja     | 6/3/2016         | DKK      | 50000                         | 50000  | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Amortyzacja     | 6/3/2016         | DKK      | 50000                         | 50000  | 2,5       | 250,000                   |
        | BUIL-00001  | 200\_SLLT | Amortyzacja     | 6/3/2016         | DKK      | 50000                         | 50000  | 2,5       | 250,000                   |

    - Wielu klientów śledziło szczegóły swoich transakcji na składnikach aktywów za pomocą skoroszytów. Szczegóły te obejmują kursy wymiany i kwoty. Jeśli masz te dane w skoroszycie, można utworzyć niestandardowy typ kursu wymiany i zaktualizować go o kursy wymiany ze skoroszytu. Ten typ kursu wymiany zostanie następnie użyty do wprowadzenia domyślnego kursu wymiany z dnia nabycia oraz obliczenia kwoty w walucie raportowania. W razie niewybrania kursu wymiany kreator użyje typu kursu wymiany zdefiniowanego w księdze.
    - Kurs wymiany i kwoty w walucie raportowania można zmieniać. Jeśli kurs wymiany ulegnie zmianie, kwota w walucie raportowania zostanie obliczona ponownie przy użyciu nowego kursu.
    - Jeśli w kreatorze wybierzesz opcję **Anuluj**, transakcje na księdze środków trwałych oraz wszelkie zmiany kursu wymiany lub kwot w walucie raportowania zostaną zapisane do czasu ponownego uruchomienia kreatora. Jednak kwoty w walucie raportowania nie zostaną zaktualizowane w transakcjach na księdze środków trwałych. Ta aktualizacja następuje tylko po wybraniu opcji **Zakończ** w kreatorze. Kreatora można uruchamiać wiele razy. W związku z tym w razie pomyłki można skorygować każdą błędną kwotę w walucie raportowania.
    - Gdy kwoty w walucie raportowania zostaną całkowicie aktualizowane w księdze podrzędnej, **należy koniecznie** ustawić opcję **Czy potwierdzasz, że zaktualizowano wszystkie kwoty w walucie raportowania w transakcjach na księdze środków trwałych?** na **Tak**, a następnie kliknąć przycisk **Zakończ**. Dopóki w opcji **Czy potwierdzasz, że zaktualizowano wszystkie kwoty w walucie raportowania w transakcjach na księdze środków trwałych?** nie zostanie ustawiona wartość **Tak**, nie można ukończyć obliczania amortyzacji. Po ustawieniu tej opcji na **Tak** kreator przestanie być dostępny.
    - Gdy transakcje na środkach trwałych w księdze podrzędnej zostaną zaktualizowane o kwoty w walucie raportowania, kwoty te nie będą pasować do kwot pierwotnie zaksięgowanych w księdze głównej. Można jednak użyć arkusza korekt w walucie raportowania w celu zaktualizowania sald kont księgowych amortyzacji w księdze głównej, tak aby pasowały do kwot pierwotnie zaksięgowanych.
    - Nowa jednostka **Kwoty transakcji na składnikach aktywów w walucie raportowania** dodana w obszarze roboczym **Zarządzanie danymi** umożliwia wyeksportowanie danych z kreatora. Następnie można użyć tych danych do ustalenia salda w księdze podrzędnej środków trwałych dla transakcji amortyzacji. Następnie tego salda można użyć do ustalania kwoty korekty w walucie raportowania w księdze głównej.

- **Uwaga dotycząca uaktualnienia:** Do środków trwałych dodano nowe pola konfiguracji, które są używane podczas obliczania amortyzacji. Może zajść potrzeba zaktualizowania tych pól przed następnym obliczaniem amortyzacji.

    - W księdze środków trwałych (**Środki trwałe** \> **Księgi**) skrócona karta **Ogólne** zawiera nowe pole **Cena nabycia w walucie raportowania**.
    - W księdze środków trwałych (**Środki trwałe** \> **Księgi**) skrócona karta **Amortyzacja** zawiera nowe pole **Oczekiwana wartość likwidacji w walucie raportowania**.
    - W oknie Parametry środków trwałych (**Środki trwałe** \> **Ustawienia** \> **Parametry środków trwałych**) skrócona karta **Ogólne** zawiera nowe pole **Minimalna kwota amortyzacji w walucie raportowania**.
    - W oknie Księgi (**środki trwałe** \> **Ustawienia** \> **Księgi**) skrócona karta **Ogólne** zawiera dwa nowe pola: **Zaokrąglenie amortyzacji w walucie raportowania** i **Pozostaw wartość księgową netto w walucie raportowania**.

- Ponieważ w propozycji amortyzacji są teraz obliczane kwoty w walucie rozliczeniowej i walucie raportowania, zaktualizowano arkusz środków trwałych, tak aby pokazywał kwoty amortyzacji w walucie raportowania. W transakcjach amortyzacji walutą transakcji jest zawsze waluta rozliczeniowa. W związku z tym te kwoty będą w dalszym ciągu wyświetlane w kolumnach **Strona debetowa** i **Strona kredytowa**. Do siatki dodano dwie nowe kolumny — **Obciążenia w walucie raportowania** i **Uznania w walucie raportowania**.

    - Nowe pola są dostępne tylko wtedy, gdy typem transakcji jeden z czterech typów amortyzacji: **Amortyzacja**, **Korekta amortyzacji**, **Amortyzacji dodatkowa** lub **Specjalny odpis amortyzacyjny**.
    - Jeśli typ transakcji amortyzacji wprowadzono w arkuszu środków trwałych, w nowych kolumnach będą wyświetlane kwoty w walucie raportowania. Kwoty te mogą być zmieniane.
    - Jeśli waluta rozliczeniowa i waluty raportowania w księdze są takie same, kwoty będą zsynchronizowane. W przypadku zmiany kwoty w kolumnie **Strona kredytowa** kwota w kolumnie **Uznania w walucie raportowania** automatycznie się odpowiednio zmieni.
    - Jeśli w arkuszu środków trwałych zostanie wprowadzony jakikolwiek inny typ transakcji, kwoty w kolumnach **Obciążenia w walucie raportowania** i **Uznania w walucie raportowania** nigdy nie są wyświetlane — ani przed zaksięgowaniem, ani po. Kwoty w walutach rozliczeniowej i raportowania są nadal dostępne w załączniku, z którego informacje są księgowane do księgi głównej.
    
### <a name="consolidations"></a>Konsolidacje
    
Funkcjonalność wprowadzona w wersji 10.0.5 Microsoft Dynamics 365 for Finance and Operations (październik 2019) umożliwia korzystanie z funkcji zarządzania funkcjami w celu zapewnienia lepszej elastyczności konsolidacji i podwójnej waluty. Aby włączyć tę funkcję, przejdź do obszaru roboczego **Zarządzanie funkcjami** i wybierz **Włącz funkcję podwójnej waluty w obszarze konsolidacja księgi głównej**.

W przypadku konsolidacji w księdze głównej dodano nową opcję w celu konsolidacji kwot w walucie rozliczeniowej lub raportowania z firm źródłowych. Jeśli waluta księgowania lub raportowania jest taka sama jak waluta księgowania lub waluta raportowania w konsolidowanej firmie, kwoty zostaną skopiowane bezpośrednio, a nie przeliczone.

-  Teraz można określić, czy w firmie źródłowej ma być używana waluta rozliczeniowa czy waluta raportowania, jako waluta transakcji w konsolidowanej firmie.

- Kwoty w walucie księgowej lub sprawozdawczej pochodzące od spółki źródłowej będą kopiowane bezpośrednio do kwot w walucie księgowej lub raportowanej w spółce konsolidacyjnej, jeżeli którakolwiek z tych walut jest taka sama. Kwoty w walucie księgowania i raportowania w konsolidowanej firmie są obliczane przy użyciu kursu wymiany, jeśli żadna z tych walut nie jest taka sama.

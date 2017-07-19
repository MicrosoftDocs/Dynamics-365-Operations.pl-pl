---
title: "Zasady zakupów"
description: "Ten artykuł zawiera informacje o zasadach zakupów. Zasady zakupów to zbiór reguł, który steruje procesem zapotrzebowań. Zasady zakupów ułatwiają administratorom zaopatrzenia wdrażanie strategii zaopatrzenia poprzez utworzenie struktury zasad dopasowanej do strategicznych wymagań zakupowych organizacji."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqSourcingPolicyRule, SysPolicy, SysPolicyListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 11614
ms.assetid: 729a304d-0f3f-4ccb-bd5b-46ee0976c57f
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 5208dc64d86345de4e53c5e293fbc861351a63ef
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017

---

# <a name="purchasing-policies"></a>Zasady zakupów

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera informacje o zasadach zakupów. Zasady zakupów to zbiór reguł, który steruje procesem zapotrzebowań. Zasady zakupów ułatwiają administratorom zaopatrzenia wdrażanie strategii zaopatrzenia poprzez utworzenie struktury zasad dopasowanej do strategicznych wymagań zakupowych organizacji.

Zasady zakupów składają się z zestawu reguł. Tworząc regułę zasad inspekcji, najpierw należy zaznaczyć typ reguły. Następnie reguła jest tworzona dla tego typu reguły przez określenie ustawień, daty początkowej i daty końcowej dla reguły.  

Na przykład, administrator tworzy zasadę, wybiera typ reguły **Reguła katalogu**, a następnie dodaje regułę katalogu do zasady. Ta reguła katalogu określa, że do zaopatrzenia wewnętrznego musi być używany katalog Adventure. Po skojarzeniu zasady zakupów z daną organizacją, pracownicy tej organizacji widzą katalog Adventure podczas tworzenia zapotrzebowania.

## <a name="assigning-policies-to-organizations"></a>Przypisywanie zasad do organizacji
Przed wejściem w życie zasady trzeba skojarzyć ją z organizacją. Zasady zakupów są kojarzone z hierarchią celów **Wewnętrzna kontrola zaopatrzenia**. Dlatego zasady zakupów dotyczą tylko organizacji w hierarchiach z celem hierarchii **Wewnętrzna kontrola zaopatrzenia**. Można też wybrać organizacje z prostej listy podmiotów prawnych w tabeli CompanyInfo. Te podmioty prawne są określone w ramach zasad jako „Firmy”.

## <a name="determining-which-rule-to-apply"></a>Określanie które reguły mają obowiązywać
W zależności od sposobu konfigurowania zasad zakupów użytkownicy w organizacji mogą być objęci wieloma regułami. Poniższe przykłady ilustrują różne sposoby konfigurowania zasad zakupów i określania, jak te zasady są stosowane w kontekście transakcji.

### <a name="example-1-simple-purchasing-policy-configuration"></a>Przykład 1: Konfigurowanie prostej zasady zakupów

W mniejszych organizacjach można konfigurować zasady zakupów według podmiotu prawnego i można w nich używać tylko hierarchii organizacyjnej Firmy.  

Dla firmy Fabrikam, która jest małą firmą, wymagania dotyczące różnią się w niewielkim stopniu w skali całej organizacji. Zasady zakupów różnią się tylko między podmiotami prawnymi organizacji. Na przykład pracownicy Fabrikam Canada i pracownicy Fabrikam USA kupują towary i usługi z różnych katalogów i od różnych dostawców. Dlatego zasady zakupów w Fabrikam zostały skonfigurowane na poziomie podmiotu prawnego.  

Fabrikam tworzy dwie zasady zakupów. Zasada A ma zastosowanie do firmy w Stanach Zjednoczonych (1111) Zasada B obowiązuje kanadyjską firmę (2222). Gdy pracownik w firmie 1111 tworzy zapotrzebowanie na zakup, reguły są pobierane z zasady A. Na przykład katalog produktów, które widzi pracownik, określono w regule katalogu dla zasady A.  

Gdy pracownik w firmie 2222 tworzy zapotrzebowanie na zakup, reguły pochodzą z zasady B.  

**Uwaga:** Jeśli pracownik firmy 1111 nabywa towar w imieniu pracownika firmy 2222, są stosowane reguły określone dla firmy 2222 (czyli reguły z zasady B).

### <a name="example-2-complex-purchasing-policy-configuration"></a>Przykład 2: Konfigurowanie złożonej zasady zakupów

W poprzednim przykładzie wszystkie reguły zakupów były zdefiniowane w jednej hierarchii organizacyjnej, tj. Firma. Jednak w złożonej organizacji może być konieczność zdefiniowania zasad dla wielu hierarchii organizacyjnych.  


Firma Contoso jest dużą firmą, która wymaga złożonych reguł zakupów do obsługi procesu zapotrzebowania. Firma Contoso zdefiniowała reguły z dwoma różnymi hierarchiami organizacyjnymi: Oddział i Globalna kontrola zakupów.  

Zasada 123 została zdefiniowana dla hierarchii organizacyjnej Dział dla firmy Sales UK — działu sprzedaży. W zasadzie 123 reguła kontroli zapotrzebowania określa, że ograniczenia muszą zostać zastosowane dla minimalnych ilości zamówienia. W tej regule wybrana jest opcja **Wymuszanie ograniczeń dotyczących minimalnej ilości zamówienia**.  

Zasada 456 jest określona dla hierarchii organizacyjnego Globalna kontrola zakupów dla działu Sprzedaż i marketing. W zasadzie 456 reguła kontroli zapotrzebowania nie określa, że ograniczenia muszą zostać zastosowane dla ilości minimalnych zamówienia. W tej regule opcja **Wymuszanie ograniczeń dotyczących minimalnej ilości zamówienia** nie jest zaznaczona.  

Sam pracuje w firmie Sales UK – dział sprzedaży w biurze firmy Contoso w Wielkiej Brytanii. W tym dziale obowiązują zasady dotyczące hierarchii organizacyjnej kontroli zakupów Dział i Globalna. Gdy Sam tworzy zapotrzebowanie na zakup, system musi określić, która zasada ma zostać zastosowana. Administrator systemu ustawia parametry zasady zakupów, by określić, że zasady zakupów muszą być stosowane w następującej kolejności:

1.  Globalna kontrola zakupów
2.  Dział
3.  Firmy

W związku z tym zasady 456 są stosowane do zapotrzebowania na zakup utworzonego przez Sama, a zamówienie na zakup nie wymaga podania minimalnej ilości.

## <a name="policy-rules"></a>Reguły zasad
### <a name="catalog-policy-rule"></a>Reguła dotycząca katalogów

Reguła dotycząca katalogów określa, który katalog zaopatrzenia widzi użytkownik podczas tworzenia zapotrzebowania na zakup. Jeśli użytkownikowi przyznano uprawnienia do zamawiania produktów w imieniu innego użytkownika, zapotrzebowanie używa reguły katalogu, która została określona dla firmy zleceniodawcy i jednostki operacyjnej w celu ustalenia katalogu, który ma być wyświetlany w witrynie zamówień. Zanim będzie można zdefiniować regułę katalogu, należy utworzyć katalog zaopatrzenia, a następnie go opublikować.

### <a name="category-access-policy-rule"></a>Reguła dostępu do kategorii

Reguła dostępu do kategorii określa kategorie, do których mają dostęp użytkownicy podczas tworzenia zapotrzebowania na zakup. Jeśli nie określono żadnych reguł, użytkownicy mogą dodawać do zapotrzebowania na zakup wszystkie kategorie zaopatrzenia.

1.  Zaznacz opcję **Uwzględnij regułę nadrzędną**, aby zastosować reguły dostępu do kategorii nadrzędnej organizacji kategorii.
2.  W okienku **Dostępne kategorie** wybierz kategorie, dla których obowiązuje reguła. Po wybraniu kategorii, wszystkie kategorie, które są wyżej w hierarchii, są również dodawane do listy **Wybrane kategorie**.
3.  Zaznacz opcję **Uwzględnij podkategorie**, aby zastosować regułę do wszystkich podkategorii w wybranej kategorii.

### <a name="category-policy-rule"></a>Reguła kategorii

Reguła kategorii określa, jak użytkownicy mogą wybrać dostawców dla każdej kategorii. Definiuje też wymagania dotyczące procesów przyjęcia i fakturowania.

### <a name="re-approval-rule-for-purchase-orders"></a>Reguła ponownego zatwierdzania zamówień zakupu

Reguła ponownego zatwierdzania jest opcjonalna i określa kryteria do wymagania ponownego zatwierdzenia w przypadku wprowadzenia zmian w zamówieniu zakupu. Wybrane pola muszą zostać ocenione w przepływie pracy zamówienia zakupu, jeśli został w nim ustawiony warunek „Wymagaj ponownego zatwierdzenia zamówienia zakupu”.

> [!NOTE]
> W przypadku zmiany zatwierdzonego zamówienie zakupu z włączonym zarządzaniem zmianami zasady podziału księgowań zawsze zostaną zresetowane. Należy więc pamiętać, że aby uniknąć konieczności ponownego zatwierdzenia zamówienia zakupu po zmianie niektórych pól, zmienione pole zasad podziału księgowań nie powinno być uwzględnione jako pole wybrane do ponownego zatwierdzania. 

### <a name="purchase-requisition-rfq-rule"></a>Reguła zapytania ofertowego do zapotrzebowania na zakup

Reguła zapytania ofertowego do zapotrzebowania na zakup określa kryteria, od których będzie zależało, czy będzie wymagane zapytanie ofertowe (ZO) na wiersz zapotrzebowania na zakup. Jeśli wiersz spełnia warunki, w wierszu zapotrzebowania pojawi się sygnatura „nieformalne ZO” lub „formalne ZO”.

### <a name="purchase-requisition-control-rule"></a>Reguła kontroli zapotrzebowania na zakup

Reguła kontroli zapotrzebowania na zakup jest opcjonalna. Podczas tworzenia reguł tego typu można ustawić opcje na poszczególnych kartach:

-   Na karcie **Przesłanie przepływu pracy** można skonfigurować pola wymagane w wierszu zapotrzebowania zapotrzebowania, które ma zostać przesłane do zatwierdzenia, jeśli celem zapotrzebowania jest **Zużycie**.
-   Na karcie **Ilości zamówienia** można skonfigurować pola, które będą wymagane w zapotrzebowaniu na zakup w określonych warunkach. Można także wymusić ilości zamówienia.
-   Na karcie **Daty** można określić, czy data księgowania jest taka sama jak data wymagalności
-   Na karcie **Adres** można określić, czy użytkownik może tworzyć nowe adresy w systemie do zastosowania w zapotrzebowaniu na zakup.

### <a name="requisition-purpose-rule"></a>Reguła celu zapotrzebowania

Reguła celu zapotrzebowania jest opcjonalna i określa typ celu zapotrzebowania dozwolony dla określonej firmy. Jeżeli w tej regule nie określono innego celu, zapotrzebowania będą miały automatycznie cel **Zużycie**.

### <a name="replenishment-category-access-policy-rule"></a>Reguła dostępu do kategorii uzupełnienia

Reguła dostępu do kategorii uzupełnienia jest opcjonalna i określa produkty dozwolone do uzupełnienia zapotrzebowania określonej firmy, gdy celem zapotrzebowania jest **Uzupełnianie zapasów**.

### <a name="replenishment-control-rule"></a>Reguła kontroli uzupełniania

Reguła kontroli uzupełniania zapasów jest opcjonalna i określa pola, które muszą być wprowadzone w wierszu zapotrzebowania dla zapotrzebowania, które ma zostać wysłane do zatwierdzenia, gdy celem zapotrzebowania jest **Uzupełnianie zapasów**.

### <a name="purchase-order-creation-and-demand-consolidation-rule"></a>Reguła tworzenia zamówienia zakupu i konsolidacji popytu

Reguła tworzenia zamówienia zakupu i konsolidacji popytu definiuje reguły, które mają być używane podczas generowania zamówienia zakupu z zatwierdzonego zapotrzebowania na zakup. Podczas tworzenia reguł tego typu można ustawić opcje na poszczególnych kartach:

-   Na karcie **Podział zamówienia zakupu** można określić kryteria podziału wierszy zapotrzebowania na zakup na osobne zamówienia zakupu.
-   Na karcie **Transfer ceny/rabatu** można zdefiniować, kiedy ponownie obliczyć umowę cenową na etapie tworzenia zamówienia zakupu:
    -   **Tylko w przypadku braku umowy handlowej** — ceny i rabaty są przenoszone z zapotrzebowania na zakup, tylko jeśli nie ma odpowiedniej umowy handlowej lub ceny bazowej. Jeśli istnieje umowa handlowa lub cena bazowa dla dostawcy lub towaru, ceny i rabaty są obliczane ponownie w oparciu o umowę handlową lub cenę bazową i stosowane do zamówienia zakupu. Jeśli nie określono inaczej, jest to działanie domyślne.
    -   **Zawsze** — ceny i rabaty zawsze są przenoszone z zapotrzebowania na zakup.

    Można również zezwalać zleceniodawcy na zmianę metody przeniesienia ceny i rabatu dla poszczególnych wierszy zapotrzebowania na zakup, niezależnie od reguły przeniesienia ceny/rabatu, która jest zdefiniowana. Zaznacz opcję **Zezwalaj na zastępowanie ręczne w wierszu zapotrzebowania zakupu**, jeśli chcesz włączyć tę możliwość.
-   Na karcie **Przeniesienie opisu pozycji** można przenosić opis towaru z zapotrzebowania, jeśli pochodzi z ZO.
-   Na karcie **Rozbieżność cenowa** można określić reguły kierowania zatwierdzonego zapotrzebowania na zakup z powrotem przez proces przeglądu, gdy zwiększa się cena towaru w katalogu zaopatrzenia. Ustaw maksymalną kwotę, o jaką może zwiększyć się kwota netto w wierszu towaru w wierszu zapotrzebowania na zakup od zatwierdzenia zapotrzebowania na zakup do utworzenia zamówienia zakupu. Kwota netto jest obliczana przy użyciu następującej formuły: (\[ilość x (cena jednostkowa – rabat) / jednostka cenowa\] + pozostałe koszty zakupu) x (100 – procent rabatu) / 100 wierszy zapotrzebowania na zakup, które przekraczają ustawioną rozbieżność cenową i są przetwarzane ręcznie. Reguły konfigurowane na karcie **Przetwarzanie błędów** określają sposób przetwarzania wierszy zapotrzebowania na zakup.
-   Na karcie **Przetwarzanie błędów**można skonfigurować regułę przetwarzania, która jest stosowana do zapotrzebowania na zakup, jeśli nie powiedzie się sprawdzanie jego poprawności podczas tworzenia zamówienia zakupu z powodu błędu rozbieżności cenowych lub błędu dostawcy. Umożliwia wybranie jednej z następujących opcji:
    -   **Brak akcji** — wiersze zapotrzebowania na zakup pozostają na stronie **Zwolnij zatwierdzone zapotrzebowania na zakup**. Stan zapotrzebowania zakupu nadal ma wartość **Zatwierdzone**. Jednak błędy muszą być najpierw uzgodnione, aby było możliwe generowanie zamówienia zakupu dla wierszy zapotrzebowania na zakup.
    -   **Anuluj wiersz zapotrzebowania na zakup** — wiersze zapotrzebowania na zakup są anulowane. W razie potrzeby zleceniodawca może tworzyć nowe zapotrzebowanie na zakup dla anulowanych wierszy.
    -   **Utwórz nowy wiersz zapotrzebowania na zakup** — wiersze zapotrzebowania na zakup są anulowane. Następnie są tworzone nowe zapotrzebowania na zakup, które zawierają wyłącznie wiersze zapotrzebowania na zakup, które nie przeszły weryfikacji. Nowo tworzone wiersze zapotrzebowania na zakup mają stan **Wersja robocza**. Te zapotrzebowania na zakup można ponownie przesłać do przeglądu po rozwiązaniu błędów weryfikacji. Wystawca zostanie powiadomiony o anulowaniu wierszy zapotrzebowania na zakup oraz utworzeniu nowych wierszy zapotrzebowań dla wierszy, które nie przeszły weryfikacji.
-   Na karcie **Ręczne tworzenie zamówienia zakupu** można określić parametry, które decydują o tym, czy zapotrzebowanie zakupu musi być ręcznie przetworzone, albo czy może być automatycznie przekonwertowane na zamówieniu zakupu. Parametry można zastosować do towarów z katalogu wewnętrznego, towarów z katalogu zewnętrznego lub towarów spoza katalogu. Umożliwia wybranie jednej z następujących opcji:
    -   **Twórz ręcznie zamówienia zakupu** — ręczne tworzenie zamówień zakupu dla wszystkich zapotrzebowań na zakup.
    -   **Automatyczne tworzenie zamówień zakupu** — automatyczne tworzenie zamówień zakupu dla wszystkich zatwierdzonych zapotrzebowań na zakup. Brak zapotrzebowań na zakup przeznaczonych do ręcznego tworzenia zamówień zakupu.
    -   **Automatycznie utwórz zamówienia zakupu, chyba że spełniają te warunki** – ręczne tworzenie zamówień zakupu dla zapotrzebowań na zakup, które spełniają kryteria zdefiniowane przez użytkownika. Wszystkie inne zapotrzebowania na zakup, które zostały zatwierdzone są automatycznie konwertowane na zamówienia zakupu. W przypadku wybrania opcji **Automatycznie utwórz zamówienia zakupu, chyba że spełniają te warunki** możesz dodawać dostawców i kategorie zaopatrzenia, aby określić zatwierdzone wiersze zapotrzebowania na zakup przeznaczone do ręcznego przetwarzania. Tę opcję można zastosować do towarów z katalogu wewnętrznego, towarów z katalogu zewnętrznego i towarów spoza katalogu. Po wybraniu kategorii zaopatrzenia wszelkie podkategorie dla tej kategorii zaopatrzenia są także wybierane. Wybór opcji **Wszystkie** spowoduje, że wszystkie wiersze zapotrzebowania na zakup określonego typu wiersza będą przetwarzane ręcznie.

    Aby automatycznie tworzyć zamówienia zakupu na podstawie zatwierdzonych zapotrzebowań na zakup za pomocą zadania wsadowego generowania zamówień zakupu, zaznacz opcję **Uruchom automatyczne tworzenie zamówienia zakupu jako zadanie wsadowe**. Ta opcja dotyczy tylko do zapotrzebowań na zakup, które nie wymagają ręcznego przetwarzania. Można zaplanować, aby uruchomienie automatycznego generowania zamówień zakupu jako zadanie wsadowe nastąpiło, gdy zasoby będą mniej ograniczone. W przypadku wybrania opcji **Wymagana zaliczka** w wierszach zapotrzebowania na zakup zaznacz opcję **Kiedy zapotrzebowanie jest skonfigurowane do zaliczki**, jeśli chcesz zatrzymywać zatwierdzone zapotrzebowania na zakup do ręcznego przetwarzania. Zapotrzebowania na zakup zatrzymane do ręcznego przetwarzania można filtrować, dzięki czemu można wyświetlić tylko te wiersze zapotrzebowania na zakup, które wymagają przedpłaty.
-   Na karcie **Konsolidacja popytu** można zdefiniować parametry, które określają, czy zapotrzebowania na zakup przetwarzane ręcznie mogą być uwzględniane w konsolidacji zapotrzebowania na zakup. Parametry można zastosować do towarów z katalogu wewnętrznego, towarów z katalogu zewnętrznego lub towarów spoza katalogu. Umożliwia wybranie jednej z następujących opcji:
    -   **Nie zezwalaj na konsolidację popytu** — brak zatwierdzonych wierszy zapotrzebowania na zakup kwalifikujących się do konsolidacji popytu. Ta opcja jest domyślnie zaznaczona i ma zastosowanie tylko do wierszy zapotrzebowania na zakup, które wymagają ręcznego przetwarzania do tworzenia zamówienia zakupu.
    -   **Zawsze zezwalaj na konsolidację popytu** — wszystkie zatwierdzone wiersze zapotrzebowania na zakup kwalifikują się do konsolidacji popytu. **Uwaga:** jeśli wybierzesz opcję **Zawsze zezwalaj na konsolidację popytu** na karcie **konsolidacji popytu**, ale zaznaczysz **Automatyczne tworzenie zamówień zakupu** na karcie **Ręczne tworzenie zamówienia zakupu**, wszystkie zapotrzebowania na zakup będą zatrzymane do ręcznego przetwarzania.
    -   **Zezwalaj na konsolidację popytu pod tymi warunkami** — służy do definiowania kryteriów, które określają, czy zatwierdzone wiersze zapotrzebowania na zakup kwalifikują się do konsolidacji popytu. Dla każdego typu wiersza zapotrzebowania na zakup można określić kryteria według dostawcy i kategorii zaopatrzenia. Po wybraniu opcji **Zezwalaj na konsolidację popytu pod tymi warunkami** dla każdego typu wiersza zapotrzebowania na zakup można określić kryteria według dostawcy i kategorii zaopatrzenia. Po wybraniu kategorii zaopatrzenia wszelkie podkategorie dla tej kategorii zaopatrzenia są także wybierane. W przypadku wybrania opcji **Wszystkie** dla określonego typu wiersza wszystkie wiersze tego typu kwalifikują się do konsolidacji popytu.






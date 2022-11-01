---
title: Automatyzuj rozliczenia księgi
description: Ten artykuł zawiera ogólne informacje o procesie automatyzacji rozliczeń księgi.
author: abruer
ms.date: 9/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: b43eeeefa581b5d8b40dc2cf0187c7c781b18be3
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708335"
---
# <a name="automate-ledger-settlements"></a>Automatyzuj rozliczenia księgi

[!include [banner](../includes/banner.md)]

W Microsoft Dynamics 365 Finance w wersji 10.0.31 funkcja  **Automatyzuj proces rozliczeń księgi** jest dostępna w przestrzeni roboczej  **Zarządzanie funkcjami** . Funkcję **Automatyczny proces rozliczania księgi** można włączyć tylko wtedy, gdy włączono funkcję **Relacja między rozliczeniem księgi a zamknięciem roku**.

Rozliczenie księgi głównej to proces dopasowywania transakcji debetowych i kredytowych w księdze głównej. Organizacje, które wykonują działania związane z rozliczeniem księgi w harmonogramie cyklicznym, mogą teraz zautomatyzować ten proces. Podczas procesu automatycznego rozliczania księgi transakcje debetowe i kredytowe mogą zostać dopasowane automatycznie tylko wtedy, gdy ich kwoty w walucie rozliczeniowej są takie same. Na przykład kwota debetu w wysokości 1,00 USD może zostać automatycznie dopasowana do kwoty kredytu 1,00 USD. Nie można jednak automatycznie dopasować wartości 1,0 USD debetowej do dwóch kredytów, z których każdy jest wyceniany na 0,50 USD. Nie jest obsługiwane częściowe uzgadnianie kwot transakcji finansowych.

Automatyzacja rozliczania księgi definiuje następujące szczegóły:

- Podczas uruchamiania rozliczeń księgi
- Które kryteria są używane w celu dopasowania kwot debetowych i kredytowych, które mogą być automatycznie rozliczane
- W jakiej kolejności są przetwarzane informacje dotyczące rozliczenia księgi

## <a name="define-the-occurrence-of-ledger-settlements"></a>Umożliwia zdefiniowanie wystąpienia rozliczeń księgi

Automatyzacja rozliczeń księgi korzysta ze struktury automatyzacji procesów. W różnych procesach biznesowych te struktury są używane do definiowania cyklu wybranego procesu. W przypadku rozliczeń księgi przejdź do  **Administracja systemem \> Ustawienia \> Automatyzacje procesów** lub **Księga główna \> Ustawienia księgi \> Automatyzacje procesów**.

Najpierw wybierz opcję **Utwórz nowy proces automatyzacji** i wybierz opcję  **Rozliczenia księgi**. Kreator przeprowadzi Cię przez proces konfigurowania automatyzacji.

## <a name="general-page"></a>Strona ogólna

Na stronie  **Ogólne** kreatora wprowadź nazwę tworzonego wystąpienia rozliczenia księgi. Jeśli na przykład pasujące obciążenia i uznania zostaną rozliczone w księdze w poniedziałek, należy wprowadzić nazwę opisową, na przykład  **LedgerSettle\_Pon**. Wana nazwa jest wyświetlana w kolumnie **Reguła automatyzacji** na stronie  **Rozliczenia księgi**.

Pozostałe ustawienia na stronie są ogólne i służą do definiowania wzorca występowania dla tej wersji rozliczeń księgi. Jeśli na przykład wystąpienie jest w poniedziałek, można je zdefiniować w taki sposób, aby było wykonywane co tydzień, a w chwili uruchamiania będzie można wybrać poniedziałek jako dzień tygodnia. Można również wprowadzić wcześniej zaplanowany czas, na przykład godz. 2:00, tak aby automatyzacja procesu była zakończona przed rozpoczęciem następnego dnia roboczego. Zaleca się zaplanowanie automatyzacji procesu, tak aby jego działanie odbywało się poza zwykłymi godzinami pracy. Dzięki temu można zmniejszyć wpływ na pracowników księgowości w ciągu dnia roboczego.

Aby uzyskać więcej informacji o innych polach na stronie  **Ogólne**, zapoznaj się z dokumentacją automatyzacji procesu.

## <a name="ledger-settlements-match-criteria-page"></a>Strona Kryteria dopasowywania rozliczeń księgi

Następną stroną w kreatorze jest strona **kryteriów dopasowania rozliczeń księgi**. Służy do definiowania kont głównych uwzględnianych w wystąpieniu automatyzacji procesu oraz kryteriów, które służą do ustalania pasujących kwot po stronie debetowej i kredytowej.

### <a name="account-selection"></a>Wybór konta

Zostaną wyświetlone konta główne, które zostały uprzednio zdefiniowane jako konta rozliczania księgi dla osoby prawnej. (Określasz konta główne jako konta rozliczenia księgi na **Księga główna \> Ustawienie księgi \> Parametry księgi głównej \> Rozliczenia księgi**).

### <a name="main-account-and-posting-layer"></a>Konto główne i warstwa księgowania

Wartości  **konta głównego** i **warstwy księgowania** są wymagane zgodnie z kryteriami dopasowania. Wartości **Konto główne** i **Warstwa księgowania** transakcji debetowej i kredytowej księgi muszą być równe, by mogły zostać dopasowane podczas procesu automatycznego rozliczania księgi.

### <a name="posting-type"></a>Typ księgowania

Wybierz opcję **Typ księgowania**, jeśli transakcje obciążeniowe i uznaniowe księgi muszą mieć taki sam typ księgowania, aby można było je dopasować podczas przetwarzania automatycznego rozliczenia księgi.

### <a name="financial-dimensions"></a>Wymiary finansowe

Wybierz opcję **Wymiary finansowe**, jeśli transakcje obciążeniowe i uznaniowe księgi muszą mieć takie same wymiary finansowe, aby można było je dopasować podczas przetwarzania automatycznego rozliczenia księgi. Po wybraniu tej opcji kryteria wartości wymiarów finansowych muszą być wybrane z listy **Dostępne wymiary finansowe**. Lista **Dostępnych wymiarów finansowych** nie zawiera wymiaru konta głównego, ponieważ jest ona automatycznie wymagana jako część kryteriów dopasowania.

## <a name="view-the-results-of-a-ledger-settlement-automation"></a>Umożliwia wyświetlenie wyników automatyzacji rozliczenia księgi

Po utworzeniu serii automatyzacji rozliczania księgi wystąpienia każdego rozliczenia księgi będą wyświetlane w widoku tygodniowym automatyzacji procesu. Ponadto wyświetlany jest stan każdego wystąpienia. Wykorzystywane są następujące stany:

- **Zaplanowane** — automatyzacja jest zaplanowana, ale nie została jeszcze uruchomiona.
- **Wykonywanie** — automatyzacja jest obecnie uruchomiona.
- **Błąd** — automatyzacja została uruchomiona, ale wystąpił błąd. Te błędy można wyświetlić, wybierając przycisk  **Wyświetl wyniki**.
- **Zakończono** — automatyzacja została pomyślnie uruchomiona. Wyniki rozliczenia można wyświetlić na stronie **Rozliczenia księgi**.

Aby wyświetlić wyniki uzgadniania, przejdź do **Księga główna \> Zadania okresowe \> Rozliczenia księgi**. Pole **Reguła automatyzacji** na stronie **Rozliczenia księgi** zawiera nazwę zadania automatycznego zaplanowanego rozliczenia księgi użytego do rozliczenia transakcji. Nieudane próby rozliczenia nie będą aktualizować wartości **Reguły automatyzacji**. Jeśli transakcja, która została wcześniej pomyślnie rozliczona przez proces automatyzacji, zostanie usunięta wartość **Reguła automatyzacji**.

W polu **Data rozliczenia** dla dopasowanego rekordu jest przedstawiana data wykonania procesu automatyzacji.

## <a name="editing-a-ledger-settlement-automation"></a>Edytowanie automatyzacji rozliczania księgi

Struktura automatyzacji procesów umożliwia edytowanie płatności, serii i wystąpień utworzonych dla rozliczania księgi. Serie można edytować na stronie  **Automatyzacja procesu** albo w widoku tygodniowym automatyzacji procesu. Na przykład, jeśli menedżer zdecyduje się rozliczyć księgę w środę zamiast w poniedziałek, może znaleźć wystąpienie w widoku tygodniowym i wybrać  **Widok/Edycja – Seria**.

W przypadku edytowania serii system monituje o określenie, czy zmiana ma być wprowadzana do wszystkich istniejących wystąpień, czy tylko do nowych wystąpień. Wystąpienia historyczne, które mają już stan **Zakończone** lub które zakończyły się ze stanem  **Błąd** nie zostaną zmienione.

Można również dodać nowe wystąpienie lub zmienić istniejące wystąpienie. Na przykład następne wystąpienie rozliczenia księgi zaplanowano na środę 1 stycznia, ale ta data jest świętem. Możesz zmienić wystąpienie z tygodniowego widoku stronyautomatyzacji procesu lub ze strony  **Automatyzacja procesu**. Zostanie otwarta strona, w której są widoczne szczegóły harmonogramu oraz kryteria dopasowania. W tym miejscu można edytować zaplanowaną datę i godzinę. Można również edytować kryteria dopasowania, jeśli są wymagane zmiany. 

Można również wyłączyć wystąpienie lub serię. Aby wyłączyć i wstrzymać przetwarzanie wystąpienia, wybierz je w widoku tygodniowym automatyzacji procesu, a następnie wybierz opcję  **Wyłącz**. Serię można wyłączyć na stronie **Automatyzacja procesu**.

## <a name="security-for-ledger-settlement-automation"></a>Bezpieczeństwo automatyzacji rozliczania księgi

Obowiązek **Zarządzaj ustawieniami serii automatyzacji rozliczeń księgi** został dodany do ról Menedżer księgowości i Kierownik ds. księgowania, a obowiązek **Wyświetl ustawienia serii automatyzacji rozliczeń księgi** został dodany do ról Księgowy, Menedżer księgowości i Kierownik ds. księgowości dla automatyzacji rozliczania księgi. Te obowiązki są domyślnymi ustawieniami zabezpieczeń, ale można je zmieniać w zależności od wymagań organizacji.

## <a name="general-ledger-parameters-for-ledger-settlement-automation"></a>Parametry księgi głównej na rzecz automatyzacji rozliczania księgi

Pole **Typowe saldo rozliczenia** wskazuje kolejność, w których będzie przetwarzane automatyczne rozliczanie księgi. Aby ustawić lub wyświetlić wartość **Typowe saldo rozliczenia**, przejdź do **Księga główna \> Ustawienia \> Parametry księgi głównej** i kartę **Rozliczenia księgi**.

Jeśli zaznaczono opcję **Debet**, proces automatycznego rozliczania księgi rozpoczyna się od strony debetowej i wyszukuje odpowiednie uznania. Jeśli zaznaczono opcję **Kredyt**, proces automatycznego rozliczania księgi rozpoczyna się od strony kredytowej i wyszukuje odpowiednie obciążenia. Ta opcja powinna odzwierciedlać typowe saldo konta głównego.

## <a name="processing-a-ledger-settlement-automation"></a>Przetwarzanie automatyzacji rozliczania księgi

Po uruchomieniu automatyzacji system wybiera transakcje księgi dla kont głównych zdefiniowanych dla serii automatyzacji procesów. Zamówienia transakcji są zamawiane według dat w zakresie dat od początku roku obrachunkowego do daty uruchomienia automatyzacji procesów. Pasuje do określonych kryteriów dopasowania. Aby rozliczyć kwotę debetu i kredytu, muszą być zgodne wartości bezwzględne kwot w walucie rozliczeniowej.

Podczas przetwarzania konta głównego w związku z wystąpieniem automatyzacji rozliczania księgi nie można go wyświetlić na stronie **Rozliczenia księgi**. Musisz czekać na ukończenie procesu automatyzacji. Aby zapobiec konfliktom, zaleca się zaplanowanie automatyzacji procesu w taki sposób, aby działał poza godzinami pracy.

Proces automatyzacji obejmuje wszystkie transakcje spełniające kryteria, z wyjątkiem transakcji, które zostały ręcznie zaznaczone do rozliczenia na stronie **Rozliczenia księgi**.

## <a name="reversal-of-transactions-that-are-settled-by-the-automation-process"></a>Wycofywanie transakcji rozliczanych w procesie automatyzacji

Można cofnąć rozliczenie, które zostało wykonane przez proces automatycznego rozliczenia księgi. Jeśli transakcja, która została wcześniej rozliczona przez proces automatyzacji zostanie wycofana, zostanie usunięta wartość **Reguła automatyzacji**.

---
title: Zlecenia kontroli jakości
description: W tym temacie opisano sposób ręcznego lub automatycznego tworzenia zleceń kontroli jakości oraz pracy z nimi w celu wykonywania inspekcji i rejestrowania wyników testu w systemie Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d06cd7766f4445a248e0394e75ae390314762cf211a2780da76b4f52aa5bccd4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739809"
---
# <a name="quality-orders"></a>Zlecenia kontroli jakości

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób ręcznego lub automatycznego tworzenia zleceń kontroli jakości oraz pracy z nimi w celu wykonywania inspekcji i rejestrowania wyników testu w systemie Microsoft Dynamics 365 Supply Chain Management.

## <a name="automatically-created-quality-orders"></a>Zlecenia kontroli jakości tworzone automatycznie

System można skonfigurować w taki sposób, aby automatycznie tworzył zlecenia kontroli jakości na podstawie reguł kontroli wyrywkowej towaru. Aby uzyskać więcej informacji, zobacz temat [Kontrola wyrywkowa towaru zarządzania jakością](quality-item-sampling.md).

## <a name="manually-create-quality-orders"></a><a name="manual-quality-orders"></a>Ręczne tworzenie zleceń kontroli jakości

Aby ręcznie utworzyć zlecenie kontroli jakości, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.
1. Wybierz pozycję **Nowy**.
1. W oknie dialogowym **Zlecenia kontroli jakości** w polu **Typ odwołania** wybierz odwołanie do zapasów, z którym będzie związane zlecenie kontroli jakości. Aby uzyskać opis dostępnych do wyboru typów odwołania, zobacz sekcję [Typy odwołania zlecenia kontroli jakości](#ref-types) w dalszej części tego tematu.

    > [!NOTE]
    > Zapasy powiązane z wybranym odwołaniem muszą być dostępne. Jeśli dla wybranej kombinacji typu odwołania, ilości i wymiarów magazynowych nie są dostępne żadne zapasy, zostanie wyświetlony komunikat o błędzie.

1. Wykonaj jedną z następujących czynności, zależnie od wartości wybranej w polu **Typ odwołania**:

    - W przypadku wybrania opcji **Zapasy** dodatkowe informacje o odwołaniu nie są wymagane.
    - W przypadku wyboru opcji **Sprzedaż** lub **Zakup** należy określić następujące informacje:

        - **Wybór konta** — odwołanie do numeru odbiorcy lub dostawcy.
        - **Numer odwołania** — odwołanie do numeru zamówienia sprzedaży lub zamówienia zakupu.
        - **Partia odwołania** — odwołanie do określonego wiersza zamówienia sprzedaży lub zamówienia zakupu.

    - Jeśli wybrano opcję **Produkcja**, **Kwarantanna** lub **Wytwarzanie produktu towarzyszącego**, w polu **Numer odwołania** należy odwołać się do numeru zlecenia produkcyjnego, zamówienia partii lub zlecenia kwarantanny.
    - W przypadku wyboru opcji **Operacja marszruty** należy określić następujące informacje:

        - **Numer odwołania** — odwołanie do numeru zlecenia produkcyjnego lub zamówienia partii.
        - **Operacja nr** — odwołanie do określonego numeru operacji marszruty.
        - **Operacja** — odwołanie do określonego numeru operacji marszruty.
        - **Zasób** — odwołanie do określonego zasobu, który musi być używany z operacją marszruty.

1. W polu **Grupa testowa** wybierz grupę testów, które muszą być wykonane.
1. W polu **Ilość** wprowadź ilość towaru, która musi zostać przetestowana.
1. W sekcji **Wymiary magazynowe** wprowadź ewentualne dodatkowe wymiary magazynowe wymagane dla wybranego towaru.
1. Kliknij przycisk **OK**.

Po utworzeniu zlecenia kontroli jakości można rozpocząć inspekcję zapasów i zarejestrować wyniki testu. Aby uzyskać więcej informacji dotyczących sposobu rejestrowania i sprawdzania poprawności wyników testu, zobacz temat [Inspekcja jakości towarów](tasks/inspect-quality-goods.md).

## <a name="quality-order-reference-types"></a><a name="ref-types"></a>Typy odwołania zlecenia kontroli jakości

Zlecenia kontroli jakości służą do śledzenia szczegółów dotyczących inspekcji i wyników testu dotyczących określonych zapasów w magazynie. Zlecenie kontroli jakości musi zawierać odwołanie reprezentujące źródło testowanych zapasów. Zlecenia kontroli jakości mogą być powiązane z następującymi typami odwołania:

- **Zapasy** — ten typ odwołania wskazuje, że sprawdzane są zapasy, które są w dostępnych zapasach. Inspekcje tego typu są zwykle losowe lub nieplanowane i są wykonywane, gdy pracownik magazynu zidentyfikuje problem.
- **Sprzedaż** — ten typ odwołania wskazuje, że sprawdzane są zapasy związane z określonym zamówieniem sprzedaży. Inspekcje tego typu są zazwyczaj związane ze specyfikacjami odbiorcy lub generowaniem certyfikatu analizy, który musi zostać dostarczony odbiorcy w ramach wysyłki. (CoA jest czasami nazywany certyfikatem zgodności \[CoC\]).
- **Zakup** — ten typ odwołania wskazuje, że sprawdzane są zapasy związane z określonym zamówieniem zakupu. Inspekcje tego typu są często używane do sprawdzania przychodzących towarów przed ich oddaniem do magazynu lub zużyciem w procesach produkcyjnych.
- **Produkcja** — ten typ odwołania wskazuje, że sprawdzane są zapasy związane z określonym zleceniem produkcyjnym. Inspekcje tego typu są często używane do sprawdzania gotowych towarów przed ich oddaniem do magazynu.
- **Kwarantanna** — ten typ odwołania wskazuje, że sprawdzane są zapasy związane z określonym zleceniem kwarantanny. Zlecenia kwarantanny są specjalnym typem zlecenia, które śledzi zapasy w segregowanym magazynie lub segregowanym obszarze w magazynie. Inspekcje tego typu są często używane do sprawdzania towarów zwróconych przez klienta lub poddanych kwarantannie w celu dalszego analizowania. Zlecenia kwarantanny mogą być generowane ze zleceń kontroli jakości. Alternatywnie mogą być generowane z innych źródeł, a następnie zlecenia kontroli jakości mogą zostać powiązane ze zleceniami kwarantanny.
- **Operacja marszruty** — ten typ odwołania wskazuje, że sprawdzane są zapasy związane z określonym krokiem marszruty zlecenia produkcyjnego. Inspekcje tego typu są zwykle używane do analizowania pracy w toku (PWT) produktu przed przejściem do następnego etapu procesu produkcji.
- **Wytwarzanie produktu towarzyszącego** — ten typ odwołania wskazuje, że sprawdzane są zapasy związane z określonym zleceniem produkcyjnym produktu towarzyszącego. Inspekcje tego typu są zwykle używane do sprawdzania produktu towarzyszącego w zamówieniu partii przed jego dodaniem do zapasów.

## <a name="view-and-create-quality-orders-from-various-parts-of-the-system"></a>Wyświetlanie i tworzenie zleceń kontroli jakości z różnych części systemu

Zlecenia kontroli jakości mogą być tworzone ręcznie. Mogą być także tworzone automatycznie na podstawie skojarzeń jakości określanych przez użytkownika. Aby uzyskać więcej informacji dotyczących tworzenia i zarządzania automatycznym tworzeniem zleceń kontroli jakości, zobacz temat [Skojarzenia jakości](quality-associations.md).

Strona zlecenia kontroli jakości umożliwia ręczne utworzenie nowego zlecenia kontroli jakości lub wyświetlenie stanu zlecenia kontroli jakości powiązanego z innym rekordem. Istnieje kilka sposobów uzyskiwania dostępu do strony zlecenia kontroli jakości.

### <a name="from-the-quality-orders-page"></a>Ze strony Zlecenia kontroli jakości

Aby ręcznie utworzyć zlecenia kontroli jakości i wyświetlić wszystkie istniejące zlecenia kontroli jakości, należy przejść do **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**. Pozostałe sekcje tego tematu zawierają więcej informacji na temat pracy ze stroną **Zlecenia kontroli jakości**.

### <a name="from-sales-orders"></a>Z zamówień sprzedaży

Aby pracować ze zleceniami kontroli jakości związanymi z zamówieniami sprzedaży, przejdź do **Sprzedaż i marketing \> Zamówienia sprzedaży \> Wszystkie zamówienia sprzedaży**, a następnie wykonaj dowolny z poniższych kroków:

- Otwórz zamówienie sprzedaży lub zaznacz je w siatce. Następnie w okienku akcji, na karcie **Pobierz i zapakuj**, w grupie **Zarządzanie jakością** wybierz **Zlecenia kontroli jakości**, aby otworzyć stronę **Zlecenia kontroli jakości**. Można tam wyświetlać, tworzyć i aktualizować zlecenia kontroli jakości powiązane z zamówieniem sprzedaży.
- Otwórz zamówienie sprzedaży, a następnie na karcie **Nagłówek** wybierz skróconą kartę **Ogólne**. W polu **Stan zlecenia kontroli jakości** jest przedstawiany ogólny stan wszystkich zleceń kontroli jakości związanych z zamówieniem sprzedaży.
- Otwórz zamówienie sprzedaży, a następnie na karcie **Wiersze** wybierz skróconą kartę **Wiersze zamówienia sprzedaży**. W kolumnie **Stan zlecenia kontroli jakości** jest przedstawiany stan każdego wiersza zamówienia sprzedaży.

### <a name="from-purchase-orders"></a>Z zamówień zakupu

Aby pracować ze zleceniami kontroli jakości związanymi z zamówieniami zakupu, przejdź do **Zaopatrzenie i sourcing \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**, a następnie wykonaj dowolny z poniższych kroków:

- Otwórz zamówienie zakupu lub zaznacz je w siatce. Następnie w okienku akcji, na karcie **Odbiór**, w grupie **Zarządzanie jakością** wybierz **Zlecenia kontroli jakości**, aby otworzyć stronę **Zlecenia kontroli jakości**. Można tam wyświetlać, tworzyć i aktualizować zlecenia kontroli jakości powiązane z zamówieniem zakupu.
- Otwórz zamówienie zakupu, a następnie na karcie **Nagłówek** wybierz skróconą kartę **Ogólne**. W polu **Stan zlecenia kontroli jakości** jest przedstawiany ogólny stan wszystkich zleceń kontroli jakości związanych z zamówieniem zakupu.
- Otwórz zamówienie zakupu, a następnie na karcie **Wiersze** wybierz skróconą kartę **Wiersze zamówienia zakupu**. W kolumnie **Stan zlecenia kontroli jakości** jest przedstawiany stan każdego wiersza zamówienia zakupu.

### <a name="from-production-orders"></a>Ze zleceń produkcyjnych

Aby pracować ze zleceniami kontroli jakości związanymi ze zleceniami produkcyjnymi, przejdź do **Kontrola produkcji \> Zlecenia produkcyjne \> Wszystkie zlecenia produkcyjne**, a następnie wykonaj dowolny z poniższych kroków:

- Otwórz zlecenie produkcyjne lub zaznacz je w siatce. Następnie w okienku akcji, na karcie **Widok**, w grupie **Zarządzanie jakością** wybierz **Zlecenia kontroli jakości**, aby otworzyć stronę **Zlecenia kontroli jakości**. Można tam wyświetlać, tworzyć i aktualizować zlecenia kontroli jakości powiązane ze zleceniem produkcyjnym.
- Otwórz zlecenie produkcyjne lub zaznacz je w siatce. Następnie na karcie **Zlecenie produkcyjne**, w grupie **Szczegóły produkcji** wybierz pozycję **Marszruta**, aby otworzyć stronę **Marszruta produkcji**. Aby wyświetlić zlecenia kontroli jakości związane z operacją marszruty, należy wykonać jedną z poniższych czynności:

    - Wybierz docelową operację marszruty w siatce. Następnie w okienku akcji wybierz pozycję **Zapytania \> Zlecenia kontroli jakości**.
    - Wybierz wartość w polu **Nr oper.** dla docelowej operacji marszruty, aby otworzyć stronę szczegółów **Marszruta produkcji**. Na skróconej karcie **Ogólne** w polu **Stan zlecenia kontroli jakości** jest przedstawiany stan zleceń kontroli jakości związanych z operacją marszruty.

- Otwórz zlecenie produkcyjne i wybierz skróconą kartę **Ogólne**. W polu **Stan zlecenia kontroli jakości** jest przedstawiany stan zleceń kontroli jakości związanych ze zleceniem produkcyjnym.

### <a name="from-quarantine-orders"></a>Ze zleceń kwarantanny

Aby pracować ze zleceniami kontroli jakości związanymi ze zleceniami kwarantanny, przejdź do **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kwarantanny**, a następnie wykonaj dowolny z poniższych kroków:

- Przejrzyj wartości w kolumnie **Stan zlecenia kontroli jakości**. W ten sposób można dowiedzieć się ogólny stan wszystkich zleceń kontroli jakości, które są powiązane z każdym zleceniem kwarantanny w siatce.
- Wybierz zlecenie kwarantanny w siatce, a następnie w okienku akcji wybierz opcję **Zlecenia kontroli jakości**, aby wyświetlić, utworzyć lub zaktualizować zlecenia kontroli jakości związane ze zleceniem kwarantanny.

## <a name="advanced-actions-for-quality-orders"></a>Zaawansowane akcje dotyczące zleceń kontroli jakości

W ramach zleceń kontroli jakości można podjąć kilka działań w celu zarządzania stanem, generowania dokumentów i generowania dodatkowych szczegółów.

### <a name="reopen-a-quality-order"></a>Ponowne otwieranie zlecenia kontroli jakości

Domyślnie nie można już edytować ani aktualizować zlecenia kontroli jakości po sprawdzeniu jego poprawności i po zakończeniu testów. Jednak w niektórych przypadkach konieczne może się okazać ponowne otwarcie zlecenia kontroli jakości po jego zakończeniu.

Aby ponownie otworzyć zlecenie kontroli jakości, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.
1. Otwórz zweryfikowane zlecenie kontroli jakości lub zaznacz je w siatce.
1. W okienku akcji kliknij opcję **Otwórz ponownie zlecenie kontroli jakości**.

### <a name="create-a-certificate-of-analysis-for-a-quality-order"></a>Tworzenie certyfikatu analizy dla zlecenia kontroli jakości

Certyfikat analizy to raport generowany przez zespół zapewnienia jakości organizacji. Weryfikuje, czy produkt spełnia określone przepisy i wymagania. Odbiorcy lub organy administracyjne w danej lokalizacji geograficznej mogą wymagać certyfikatów analizy. Mogą one również być wymagane w zależności od branży oraz typu produktów obsługiwanych, kupowanych, wytwarzanych lub sprzedawanych.

Moduł Supply Chain Management umożliwia generowanie certyfikatów analizy ze zleceń kontroli jakości. Raport będzie zawierał wyniki wszystkich testów zlecenia kontroli jakości, w których opcja **Raport certyfikatu analizy** jest ustawiona na wartość *Tak*. Tę opcję można ustawić domyślnie na podstawie testu, który zdefiniowano na stronie **Testy**. Ustawienie to można jednak zastąpić dla określonych towarów lub określonego zlecenia kontroli jakości.

Aby wygenerować certyfikat analizy dla zlecenia kontroli jakości, należy wykonać następujące czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zadania okresowe \> Zarządzanie jakością \> Zlecenia kontroli jakości**.
1. Wybierz zlecenie kontroli jakości, dla którego chcesz utworzyć zlecenie kontroli jakości.
1. W okienku akcji wybierz **Zapytania \> Certyfikat analizy**.
1. Na stronie **Certyfikat analizy**, w okienku akcji wybierz **Nowy**.
1. Opcjonalnie: w polu **Osoba kontaktowa** wybierz osobę kontaktowa, do której ma być adresowany certyfikat.
1. W okienku akcji wybierz opcję **Drukuj**.
1. W oknie dialogowym **Certyfikat analizy** określ sposób drukowania raportu. Następnie wybierz przycisk **OK**, aby wydrukować raport na drukarce, na ekranie, do pliku lub do wiadomości e-mail.
1. Zamknij strony.

### <a name="block-or-unblock-inventory-for-a-quality-order"></a>Blokowanie lub odblokowywanie zapasów dla zlecenia kontroli jakości

Gdy zlecenie kontroli jakości jest generowane automatycznie na podstawie skojarzenia jakości, kontrolę wyrywkową towaru przypisaną do skojarzenia jakości można tak skonfigurować, aby zablokować pełną ilość zapasów odwołania, które jest testowane. Aby uzyskać więcej informacji na temat kontroli wyrywkowej towarów, zobacz temat [Kontrola wyrywkowa towarów w zarządzaniu jakością](quality-item-sampling.md).

Jeśli nie jest wykonywane pełne blokowanie lub jeśli zlecenie kontroli jakości jest tworzone ręcznie, system automatycznie tworzy rekord blokowania zapasów dla testowanego towaru w zleceniu kontroli jakości. W rekordzie utworzonym na stronie **Blokowanie zapasów** pole **Typ blokowania zapasów** ma wartość *Zlecenie kontroli jakości*.

Aby wyświetlić i edytować blokowanie zapasów dla zlecenia kontroli jakości wybranego na stronie **Blokowanie zapasów**, wybierz pozycje **Zapytanie \> Blokowanie zapasów** w okienku akcji. Aby uzyskać więcej informacji, zobacz [Blokowanie zapasów](inventory-blocking.md).

### <a name="inquire-about-the-details-of-a-quality-order"></a>Zapytanie o szczegóły zlecenia kontroli jakości

Za pomocą następujących przycisków na okienku akcji na stronie **Zlecenia kontroli jakości** można wyświetlić więcej informacji dotyczących zlecenia kontroli jakości lub związanych z nim:

- **Zapytania \> Szczegóły pracy** — Umożliwia otwarcie strony, na której można przejrzeć pracę magazynową związaną ze zleceniem kontroli jakości.
- **Zapytania \> Informacje o niezgodnościach** — Umożliwia otwarcie strony, na której można przejrzeć wszystkie niezgodności związane ze zleceniem kontroli jakości.
- **Zapasy** — polecenia dostępne w tym menu są wspólne dla wszystkich transakcji magazynowych. Można ich używać do wyświetlania i aktualizowania szczegółów, takich jak transakcje, stan dostępnych zapasów, rezerwacje i zaznaczanie.

### <a name="create-cases-related-to-quality-orders"></a>Tworzenie spraw związanych ze zleceniami kontroli jakości

Istnieje możliwość tworzenia spraw związanych ze zleceniami kontroli jakości. W ten sposób można śledzić szczegóły dotyczące problemów i pracować nad rozwiązaniem. Następnie można użyć funkcji przepływu pracy zarządzania sprawami, aby kierować sprawę przez wstępnie zdefiniowany proces biznesowy w celu uzyskania dodatkowych zatwierdzeń lub dalszych informacji na temat określonego problemu. Można również użyć funkcji artykułów merytorycznych, aby utworzyć bazę wiedzy rozwiązań typowych problemów.

## <a name="case-management-examples-for-quality-management"></a>Przykłady zarządzania sprawami dla zarządzania jakością

### <a name="example-1"></a>Przykład 1

Pracujesz w firmie produkcyjnej, która musi przestrzegać ścisłych przepisów związanych z produkcją produktów podlegających regulacjom prawnym, takich jak żywność. Zlecenia kontroli jakości są używane do rejestracji i śledzenia szczegółów dotyczących jakości towarów w całym procesie produkcji. Jeśli zlecenie kontroli jakości nie przejdzie określonych testów, może występować problem ze sprzętem. Sprawy są używane w celu śledzenia procesu biznesowego i eskalacji problemu do poprawnych inżynierów, aby można było ustalić główną przyczynę. Aby ułatwić korzystanie z procesów biznesowych, firma przechowuje bazę wiedzy na temat typowych problemów związanych ze zleceniami kontroli jakości i problemami ze sprzętem.

### <a name="example-2"></a>Przykład 2

Pracujesz dla firmy dystrybucyjnej wysyłającej produkty, które można dostosowywać do różnych krajów i regionów. Niektórzy odbiorcy mają ściśle określone specyfikacje. W przeciwnym razie mogą wystąpić opłaty i zwroty lub obciążenia zwrotne. Za pomocą zleceń kontroli jakości można śledzić szczegóły dotyczące poszczególnych testów i wyników, które spełniają wymagania klientów. Sprawy służą do przeglądania i zatwierdzania szczegółów certyfikatu analizy przed wygenerowaniem dokumentu i dodaniem go razem z inną dokumentacją wysyłkową.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Procesy zarządzania jakością](quality-management-processes.md)
- [Test jakości](quality-tests.md)
- [Grupy testów jakości](quality-test-groups.md)
- [Powiązania jakości](quality-associations.md)
- [Procesy zarządzania jakością](quality-management-processes.md)
- [Włączanie zarządzania kontrolą jakości i niezgodnością](enable-quality-management.md)
- [Zarządzanie jakością dla procesów magazynowych](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

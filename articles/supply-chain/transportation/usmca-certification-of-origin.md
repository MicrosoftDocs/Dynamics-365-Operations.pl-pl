---
title: Certyfikacja pochodzenia USMCA
description: Ta funkcja umożliwia wydrukowanie dokumentów świadectwa pochodzenia wymaganych przez umowę Stany Zjednoczone-Meksyk-Kanada (USMCA).
author: Henrikan
ms.date: 10/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-23
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: a84751da6e9303ed9ffe0f0b5aa6c12512e0fa624a5a2e0c7d85ebbffad0669a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726592"
---
# <a name="usmca-certification-of-origin"></a>Certyfikacja pochodzenia USMCA

[!include [banner](../includes/banner.md)]

Ta funkcja umożliwia wydrukowanie dokumentów świadectwa pochodzenia wymaganych przez umowę Stany Zjednoczone-Meksyk-Kanada (USMCA).

*Dokument USMCA świadectwa pochodzenia* zawiera minimalne elementy danych wymagane w deklaracji. Niektóre elementy danych można wstępnie wypełniać przed drukowaniem, podczas gdy inne muszą być wypełniane ręcznie po wydrukowaniu. W celu uzyskania preferencyjnego traktowania taryfowego dokument musi zostać wypełniony i w posiadaniu importera w momencie dokonywania zgłoszenia. Dokument może zostać wypełniony przez importera, eksportera lub producenta.

Dokument można wydrukować dla jednej wysyłki na stronie listy **Wszystkie wysyłki** lub na stronie **Szczegóły wysyłki**.

Dokument jest dostępny tylko wtedy, gdy krajem w podstawowym adresie osoby prawnej są Stany Zjednoczone.

W zależności od opcji drukowania dokumentu dokument może być wstępnie wypełniony danymi z systemu. Istnieje możliwość zmiany lub dodania danych do drukowanego dokumentu przez wyeksportowanie wydrukowanego dokumentu do formatu edytowalnego, np. Microsoft Word. Po zakończeniu eksportu można zastosować wszelkie wymagane zmiany przed dokonaniem danej deklaracji.

## <a name="turn-on-the-usmca-feature"></a>Włączanie funkcji USMCA

Aby móc używać funkcji USMCA, należy ją włączyć w systemie. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł**: *Zarządzanie transportem*
- **Nazwa funkcji:** *Certyfikat USMCA dokumentu pochodzenia*

## <a name="document-content"></a>Zawartość dokumentu

Certyfikat USMCA dokumentu pochodzenia zawiera następujące elementy danych:

- Elementy adresu
- Rola strony certyfikującej
- Pojedyncza wysyłka
- Faktury
- Okres zbiorczy
- Szczegóły towaru
- Podpis osoby poświadczającej
- Liczba stron

Aby uzyskać więcej informacji na temat każdego z tych elementów i sposobu znalezienia ich wartości, zapoznaj się z pozostałymi sekcjami w tym temacie.

## <a name="print-a-usmca-certification-of-origin-document"></a>Drukowanie certyfikatu USMCA dokumentu pochodzenia

Aby wydrukować certyfikat USMCA dokumentu pochodzenia dla wysyłki, należy wykonać następujące czynności:

1. Wykonaj jedną z następujących czynności:
    - Przejdź do modułu **Zarządzanie transportem wysyłek > Wysyłki > Wszystkie wysyłki** i wybierz wysyłkę, dla której ma zostać wydrukowany dokument.
    - Otwórz stronę **Szczegóły wysyłki** dla wysyłki, dla której ma zostać wydrukowany dokument (istnieje kilka sposobów, jak to zrobić, w tym na stronie **Wszystkie wysyłki**).
1. W okienku akcji otwórz kartę **Wysyłki**, a następnie w grupie **Drukuj** wybierz opcję **Certyfikat pochodzenia USMCA**.
1. Zostanie otwarte okno dialogowe **Certyfikat lub pochodzenie**. Określ ustawienia opisane w poniższych podsekcjach, a następnie kliknij przycisk **OK**, aby wygenerować dokument.
1. Otworzy się podgląd dokumentu. Aby w razie potrzeby wydrukować lub wyeksportować dokument, należy skorzystać z poleceń dostępnych w okienku akcji.

### <a name="certifying-party"></a>Strona certyfikująca

Lista rozwijana **Jednostka certyfikująca** służy do identyfikowania typu strony, która drukuje dokument. Określ, czy strona certyfikująca jest *eksporterem*, *eksporterem i producentem*, *producentem* lub *importerem* lub pozostaw to pole puste, jeśli strona certyfikująca nie jest żadną z tych opcji. Wybrana opcja określa, co ma być drukowane w sekcjach adresowych dokumentu.

Wybrana **Strona certyfikująca** zostanie uwzględniona w wydrukowanym dokumencie.

Dokument można wydrukować zarówno dla wydań przychodzących, jak i wychodzących. Wybierz *Importera* jako **Stronę certyfikującą** tylko dla wydań przychodzących.

W poniższej tabeli opisano typy informacji, które znajdują się w dokumencie na podstawie wybranej przez użytkownika **Strony certyfikującej**.

| Strona&nbsp;certyfikująca | opis |
|---|---|
| *\[Pusty\]* | Dodaje do dokumentu następujące szczegóły:<ul><li>**Szczegóły podmiotu certyfikującego**: używane są szczegóły adresu dla magazynu, jeśli są dostępne; w przeciwnym razie korzysta z adresu oddziału wysyłkowego, jeśli jest dostępny; w przeciwnym razie używa adresu osoby prawnej (firmy) wybranej w module Supply Chain Management.</li><li>**Szczegóły eksportera**: puste</li><li>**Szczegóły producenta**: puste</li><li>**Szczegóły importera**: puste</li><ul>|
| *Eksporter* | Dodaje do dokumentu następujące szczegóły:<ul><li>**Szczegóły podmiotu certyfikującego**: używane są szczegóły adresu dla magazynu, jeśli są dostępne; w przeciwnym razie korzysta z adresu oddziału wysyłkowego, jeśli jest dostępny; w przeciwnym razie używa adresu osoby prawnej (firmy) wybranej w module Supply Chain Management.</li><li>**Szczegóły eksportera**: używa szczegółów adresu dla osoby prawnej.</li><li>**Szczegóły producenta**: puste</li><li>**Szczegóły importera**: używa konta faktury dla powiązanego zamówienia sprzedaży.</li><ul>|
| *Eksporter i producent* | Dodaje do dokumentu następujące szczegóły:<ul><li>**Szczegóły podmiotu certyfikującego**: używane są szczegóły adresu dla magazynu, jeśli są dostępne; w przeciwnym razie korzysta z adresu oddziału wysyłkowego, jeśli jest dostępny; w przeciwnym razie używa adresu osoby prawnej (firmy) wybranej w module Supply Chain Management.</li><li>**Szczegóły eksportera**: używa szczegółów adresu dla osoby prawnej.</li><li>**Szczegóły producenta**: używa szczegółów adresu dla osoby prawnej.</li><li>**Szczegóły importera**: używa konta faktury dla powiązanego zamówienia sprzedaży.</li><ul>|
| *Importer* | Dodaje do dokumentu następujące szczegóły:<ul><li>**Szczegóły podmiotu certyfikującego**: używane są szczegóły adresu dla magazynu, jeśli są dostępne; w przeciwnym razie korzysta z adresu oddziału wysyłkowego, jeśli jest dostępny; w przeciwnym razie używa adresu osoby prawnej (firmy) wybranej w module Supply Chain Management.</li><li>**Szczegóły eksportera**: puste</li><li>**Szczegóły producenta**: puste</li><li>**Szczegóły importera**: używa szczegółów adresu dla osoby prawnej.</li><ul>|
| *Producent* | Dodaje do dokumentu następujące szczegóły:<ul><li>**Szczegóły podmiotu certyfikującego**: używane są szczegóły adresu dla magazynu, jeśli są dostępne; w przeciwnym razie korzysta z adresu oddziału wysyłkowego, jeśli jest dostępny; w przeciwnym razie używa adresu osoby prawnej wybranej w module Supply Chain Management.</li><li>**Szczegóły eksportera**: puste</li><li>**Szczegóły producenta**: używa szczegółów adresu dla osoby prawnej.</li><li>**Szczegóły importera**: puste</li><ul>|

### <a name="has-various-producers"></a>Ma różnych producentów

Lista rozwijana **Strony certyfikującej** kontroluje tekst, który ma być użyty w szczegółach dotyczących producenta w dokumencie. Wybierz jedną z następujących opcji:

- *Różni producenci* — drukuje tekst „Różni” w szczegółach producenta.
- *Dostępne na zażądanie* — drukuje tekst „Dostępne na żądanie władz dokonujących przywozu” w szczegółach producenta.

Jeśli **Strona certyfikująca** jest ustawiona na *Eksportera i producenta* lub *Producenta*, to ustawienie **Ma różnych producentów** jest unieważnione, a szczegóły adresu producenta będą takie same jak podmiotu certyfikującego.

### <a name="blanket-period"></a>Okres zbiorczy

Użyj ustawień **Okres zbiorczy od** i **Okres zbiorczy do** w celu określenia okresu zbiorczego, podczas którego dokument będzie obejmował wiele wysyłek identycznych towarów, nawet jeśli dokument zostanie wydrukowany tylko dla jednej wysyłki. Daty okresu zbiorczego można ustawiać bez ograniczeń i zostaną one dodane do dokumentu. Te ustawienia można również pozostawić puste lub je skonfigurować w przeszłości.

### <a name="is-single-shipment"></a>W pojedynczej wysyłce

W oknie dialogowym **Certyfikat pochodzenia** należy skonfigurować **W pojedynczej wysyłce** w jednej z następujących opcji:

- *Tak* — dodaje opcję „Pojedyncza wysyłka: tak” obok numeru faktury.
- *Nie* — nic nie dodaje.

## <a name="other-information-included-in-the-document"></a>Inne informacje zawarte w dokumencie

Oprócz opcjonalnych elementów, które wybiera się za pomocą okna dialogowego **Certyfikat lub pochodzenie**, certyfikacja USMCA dokumentu pochodzenia będzie zawierać informacje i pola niestandardowe zestawione w poniższych podsekcjach. Niektóre z tych informacji należy wprowadzić ręcznie po wygenerowaniu dokumentu.

### <a name="invoice-number"></a>Numer faktury

Identyfikatory faktur sprzedaży związanych z wysyłkami są drukowane na dokumencie niezależnie od okresu zbiorczego. Numery faktur są drukowane niezależnie od tego, czy wybrano **W jednej wysyłce**.

### <a name="item-details"></a>Szczegóły towaru

Dokument zawiera kilka sekcji, w których wyszczególniono konkretne szczegóły dotyczące pozycji:

- **Numer SKU**: drukuje numer pozycji zwolnionego produktu.

- **Opis**: drukuje opis lub nazwę zwolnionego produktu. Jeśli istnieje opis w języku użytkownika, jest on drukowany. Jeśli brak takiego opisu, nazwa jest drukowana w języku użytkownika. Jeśli taka nazwa nie istnieje, zostanie wydrukowana nazwa pozycji.

- **Klasyfikacja taryfowa systemu ujednoliconego (SU)**: drukuje ujednolicony harmonogram taryfowy skojarzony z produktem. Te harmonogramy można skonfigurować, przechodząc do ustawień **Zarządzanie transportem \> Ustawienia \> Standard transportu \> Ujednolicone harmonogramy taryfowe**.

- **Kryterium pochodzenia:** podczas pierwszego zwalniania dokumentu konieczne jest ręczne wprowadzenie danych w tej sekcji.

- **Kraj pochodzenia:** drukuje kraj pochodzenia, który ma zostać zastosowany po przejściu do **Zarządzanie informacjami o produkcie \> Ustawienia \> Zgodność produktu \> Kraj pochodzenia** (patrz także [Kraj pochodzenia](../pim/country-of-origin.md)). Kod ISO dla kraju pochodzenia jest drukowany na podstawie kraju/regionu docelowego w adresie dostawy wysyłki i pozycji. Jeśli nie skonfigurowano żadnego kraju pochodzenia danych, ta wartość zostanie przywrócona do ustawienia znalezionego w obszarze **Zwolniony produkt \> Handel zagraniczny \> Pochodzenie**. Jeśli nadal nie zostaną znalezione dane kraju pochodzenia, należy ręcznie wprowadzić kraj pochodzenia po wygenerowaniu dokumentu.

### <a name="certifier-signature-and-date"></a>Podpis osoby poświadczającej i data

Należy wprowadzić je ręcznie po wygenerowaniu dokumentu.

### <a name="consists-of-number-of-pages"></a>Składa się z liczby stron

Użytkownik podpisujący certyfikat musi ręcznie wprowadzić liczbę stron (do weryfikacji) po wygenerowaniu dokumentu.

### <a name="page-numbers"></a>Numery stron

Bieżąca strona i liczba stron wydrukowanych u dołu dokumentu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
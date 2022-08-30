---
title: Rozliczanie konserwacji składników majątku należących do klienta
description: W tym artykule wyjaśniono, jak tworzyć, przetwarzać i rozliczać prace konserwacyjne wykonane dla składników majątku należących do klienta.
author: johanhoffmann
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjProjectContractsListPage, ProjInvoiceTable, ProjProjectsListPage, ProjTable, EntAssetWorkOrderType, EntAssetWorkOrderProjectSetup, EntAssetObjectTable, EntAssetWorkOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c0d067ec4f2110b1c146ef0229b90e309578eaa7
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335084"
---
# <a name="bill-for-maintenance-on-customer-owned-assets"></a>Rozliczanie konserwacji składników majątku należących do klienta

[!include [banner](../../includes/banner.md)]

Funkcja *rozliczania zleceń pracy* umożliwia tworzenie, przetwarzanie i rozliczanie prac konserwacyjnych dotyczących składników majątku należących do klientów. Ta funkcja pozwala wykonać następujące zadania:

- Połącz odbiorców z posiadanymi przez nich składnikami majątku.
- Wybierz klienta i wyświetl składniki majątku, których właścicielem jest klient, podczas tworzenia zlecenia pracy.
- Skonfiguruj projekt nadrzędny dla każdego klienta.
- Zarejestruj godziny, pozycje, wydatki i opłaty względem zlecenia pracy, a następnie utwórz propozycję faktury dla odbiorcy później.

Ponadto ta funkcja udostępnia następujące funkcje:

- Umowa projektu z nadrzędnego projektu odbiorcy jest automatycznie kopiowana do odpowiedniego projektu zlecenia pracy.
- Zarządzanie składnikami majątku może teraz używać typu transakcji projektu *opłaty* zarówno w prognozach, jak i w arkuszach zleceń pracy.

## <a name="turn-on-the-customer-billing-feature"></a>Włącz funkcję rozliczania klientów

Aby używać tej funkcji, należy ją włączyć dla systemu. Administratorzy mogą skorzystać z ustawień [zarządzania funkcją](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł:** *Zarządzanie projektami i ich księgowanie*
- **Nazwa funkcji:** *Rozliczanie zlecenia pracy*

## <a name="example-scenario"></a>Przykładowy scenariusz

Aby się dowiedzieć, jak działa ta funkcja, należy przejść do poniższego przykładowego scenariusza.

Aby pracować z tym scenariuszem przy użyciu określonych przykładowych rekordów i wartości tutaj określonych, należy użyć systemu, w którym są zainstalowane standardowe [dane demonstracyjne](../../../fin-ops-core/fin-ops/get-started/demo-data.md). Należy wybrać firmę **USMF** przed rozpoczęciem.

Tego scenariusza można również używać jako wskazówek dotyczących danej funkcji podczas pracy w produkcji. Jednak w takim przypadku trzeba podstawiać własne wartości i w niektórych przypadkach może brakować pewnych typów wymaganych rekordów, które są dostępne w standardowych danych demonstracyjnych.

### <a name="step-1-create-a-new-project-contract-for-the-customer"></a>Krok 1: Tworzenie nowej umowy dotyczącej projektu dla klienta

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie \> Projekty \> Umowy dotyczące projektu**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Nowa umowa dotycząca projektu** można ustawić następujące wartości:

    - **Nazwa:** *Pelican Wholesales*
    - **Typ finansowania:** *Klient*
    - **Źródło finansowania:** *US-013* (*Pelican Wholesales*)

1. Kliknij przycisk **OK**.

### <a name="step-2-create-a-new-parent-project-for-the-customer"></a>Krok 2: Tworzenie nowego projektu nadrzędnego dla klienta

Utworzony tutaj projekt nadrzędny będzie używany podczas tworzenia zleceń pracy dla odbiorcy.

1. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie \> Projekty \> Wszystkie projekty**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Nowy projekt** można ustawić następujące wartości:

    - **Typ projektu:** *Czas i materiały*
    - **Nazwa projektu:** *Zlecenia pracy Pelican Wholesales*
    - **Grupa projektów:** *TM*
    - **Identyfikator umowy projektu:** *Pelican Wholesales* (wcześniej utworzona umowa)
    - **Data początkowa**: wybierz dzisiejszą datę.

1. Wybierz opcję **Utwórz projekt**.
1. Nowy projekt jest otwarty. Zanotuj wartość **identyfikatora projektu**. Trzeba będzie go wprowadzić później.

### <a name="step-3-create-a-new-work-order-type-in-asset-management"></a>Krok 3: Tworzenie nowego typu zlecenia pracy w zarządzaniu składnikami majątku

1. Przejdź do pozycji **Zarządzanie składnikami majątku \> Konfiguracja \> Zlecenie pracy \> Typy zleceń pracy**.
1. W okienku akcji wybierz opcję **Nowy**.
1. Nowy rekord zostanie dodany do listy. Należy dla niego określić następujące wartości:

    - **Typ zlecenia pracy:** *Usługa*
    - **Nazwa:** *Zlecenia pracy usług*
    - **Stan cyklu życia zlecenia pracy:** *Standardowy*

### <a name="step-4-link-the-customer-account-to-the-parent-project"></a>Krok 4: Łączenie konta klientem z projektem nadrzędnym

Teraz musisz połączyć konto klienta z projektem nadrzędnym w ustawieniach projektu w zarządzaniu składnikami aktywów.

1. Przejdź do **Zarządzanie składnikami majątku \> Konfiguracja \> Zlecenia pracy \> Ustawienia projektu**.
1. Na karcie **Projekt nadrzędny** wybierz opcję **Dodaj**, aby dodać wiersz.
1. W nowym wierszu ustaw następujące wartości:

    - **Konto klienta:** *US-013* (*Pelican Wholesales*)
    - **Identyfikator projektu**: wprowadź identyfikator projektu zanotowany wcześniej.

### <a name="step-5-link-the-project-group-and-type-to-the-work-order-project"></a>Krok 5: Łączenie grupy projektów i ustawianie typu projektu zlecenia pracy

Użytkownik nadal powinien być na stronie **Ustawienia projektu** (**Zarządzanie składnikami majątku \> Ustawienia \> Zlecenia pracy \> Ustawienia projektu**).

1. Na karcie **Grupa projektów** wybierz opcję **Dodaj**, aby dodać wiersz.
1. W nowym wierszu ustaw następujące wartości:

    - **Typ zlecenia pracy:** *Usługa* (typ zlecenia pracy utworzony wcześniej)
    - **Grupa projektów:** *TM*

> [!NOTE]
> Umowa projektu w projekcie zlecenia pracy jest zawsze dziedziczona po projekcie nadrzędnym.

### <a name="step-6-link-an-asset-to-the-customer-id"></a>Krok 6: Łączenie składnika majątku z identyfikatorem klienta

1. Wybierz **Zarządzanie składnikami majątku \> Składniki majątku \> Aktywne składniki majątku**.
1. W polu **Filtruj** wprowadź *VE-102* i wybierz opcję filtrowania według **składnika majątku**.
1. Wybierz składnik majątku, aby otworzyć ustawienia.
1. Na skróconej karcie **Odbiorca**, w polu **Konto odbiorcy**, należy ustawić wartość *US-013* (*Pelican Wholesales*).

    Pole **Nazwa** jest automatycznie aktualizowana do wartości *Pelican Wholesales*.

### <a name="step-7-create-a-new-work-order-on-the-asset"></a>Krok 7: Tworzenie nowego typu zlecenia pracy w składniku majątku

1. Przejdź do pozycji **Zarządzanie składnikami majątku \> Zlecenia pracy \> Aktywne zlecenia pracy**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W wyświetlonym oknie dialogowym **Utwórz zlecenie pracy** można ustawić następujące wartości:

    - **Typ zlecenia pracy:** *Usługa*
    - **Opis:** *Naprawa ciężarówki*
    - **Konto klienta:** *US-013* (*Pelican Wholesales*)
    - **Składnik majątku:** *VE-102*

        > [!NOTE]
        > W wynikach wyszukiwania są dostępne tylko te składnik majątku, które są połączone z wybranym kontem odbiorcy.

    - **Typ zadania konserwacji:** *Naprawa*
    - **Zawód:** *Mechanik*
    - **Poziom usług:** *4*

1. Kliknij przycisk **OK**.

### <a name="step-8-review-the-work-order-and-start-to-work-on-it"></a>Krok 8: Przeglądanie zlecenia pracy i rozpoczynanie pracy

W tej sekcji będziesz pracować nad zleceniem pracy utworzonym w poprzedniej sekcji.

1. Aby sprawdzić, czy projekt nadrzędny to projekt *Zlecenie pracy Pelican Wholesales*, wykonaj następujące czynności:

    1. W sekcji **Zadania konserwacji zlecenia pracy** wybierz wiersz.
    1. Na skróconej karcie **Szczegóły wiersza** sprawdź wartość **identyfikatora projektu**. Powinien to być numer z łącznikiem w następującej postaci: *\<Parent-Project-ID\>-\<Project-ID\>*. Ta wartość jest linkiem.
    1. Wybierz link identyfikatora projektu, aby otworzyć stronę, na której możesz przejrzeć projekt nadrzędny i nazwy projektów.

1. W okienku akcji, na karcie **Zlecenie pracy**, w grupie **Stan cyklu życia** wybierz **Aktualizuj stan zlecenia pracy**.
1. W oknie dialogowym **Aktualizuj stan zlecenia pracy** w kolumnie **Wybierz** zaznacz pole wyboru dla wiersza, w którym w polu **Stan cyklu życia** ustawiono wartość *W toku*.
1. Kliknij przycisk **OK**.
1. W oknie dialogowym **Stan cyklu życia: W toku** wybierz przycisk **OK**.

### <a name="step-9-post-the-hours-that-were-spent-on-the-work-order-and-create-a-new-invoice-proposal"></a>Krok 9: Księgowanie godzin spędzonych na pracy ze zleceniem i tworzenie nowej propozycji faktury

W tej sekcji będziesz nadal pracować nad zleceniem pracy, nad którym rozpoczęto pracę w poprzedniej sekcji.

1. W okienku akcji na karcie **Zlecenie pracy**, w grupie **Projekt** kliknij **Arkusze**.

    Zostanie wyświetlona strona **Arkusze zlecenia pracy**. W tym miejscu można rejestrować czas, który użytkownik poświęcił na zlecenie pracy.

1. Na skróconej karcie **Godziny** wybierz pozycję **Dodaj wiersz**.
1. W nowym wierszu ustaw w polu **Godziny** wartość *4*.
1. W okienku akcji wybierz pozycję **Księguj arkusze**.
1. Zamknij stronę **Arkusze zlecenia pracy**, aby powrócić do zlecenia pracy.
1. W okienku akcji na karcie **Fakturowanie** wybierz opcję **Nowa propozycja faktury**.
1. W oknie dialogowym **Tworzenie propozycji faktury** w sekcji **Transakcje projektu** zaznacz pole wyboru **Wybierz** dla każdego wiersza, który chcesz zafakturować.
1. Naciśnij przycisk **OK**, aby zamknąć okno dialogowe i wyświetlić nową propozycję faktury.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
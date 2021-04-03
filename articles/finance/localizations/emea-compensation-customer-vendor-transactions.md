---
title: Konfiguracja kompensacji odbiorców oraz dostawców
description: Ten temat zawiera informacje o sposobach wykonywania procesu kompensat na kontach dostawców i odbiorców dla firm, które mają podstawowy adres działalności na Węgrzech lub w Polsce.
author: mrolecki
manager: AnnBe
ms.date: 05/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustVendCompensation, VendTable, CustTrans, VendTrans
audience: Application User
ms.reviewer: kfend
ms.custom: 1691503
ms.search.region: Hungary, Poland
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63fe1d081a80efa0fc794bf2f223d59019f6f908
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236314"
---
# <a name="set-up-customer-and-vendor-compensation"></a>Konfiguracja kompensacji odbiorców oraz dostawców

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje, które pomogą wykonywać proces kompensat na kontach dostawców i odbiorców dla firm, które mają podstawowy adres działalności na Węgrzech lub w Polsce.

Często użytkownicy w Europie Wschodniej muszą rozliczać kwoty należności i zobowiązań dla firmy, która jest zarejestrowana w systemie równocześnie jako odbiorca i dostawca. Ten proces rozliczania wykorzystuje prawną procedurę znaną jako *kompensata* lub *netowanie* (netting). 

## <a name="enabling-compensation"></a>Włączanie kompensowania

### <a name="set-up-compensation-notes"></a>Konfigurowanie notek kompensacyjnych
Można skonfigurować notki, które będą drukowane w dokumentach kompensaty. Stronę **Notatki** można otworzyć ze strony **Ustawienia** > **Formularze** w modułach Rozrachunki z odbiorcami, Rozrachunki z dostawcami lub Zarządzanie projektami i ich księgowanie.

Tworząc nową notatkę formularza, można wybrać część dokumentu kompensaty, której notatka ma dotyczyć:

 - **Dokument kompensaty — nagłówek** — górna części dokument kompensaty, na przykład z nazwą firmy.
 - **Dokument kompensaty — należności** — treść dokumentu kompensaty należności.
 - **Dokument kompensaty — zobowiązania** — treść dokumentu kompensaty zobowiązań.
 - **Dokument kompensaty — salda** — treść dokumentu kompensaty salda.

Można wprowadzić notkę dla każdej odnośnej kombinacji notatki formularza i języka.

Notatka formularza jest oparta na znaku matematycznym kwoty salda w raporcie o kompensacie:

- Jeśli kwota salda jest większa niż 0 (zero), jest drukowana notka o kompensacie należności.
- Jeśli kwota salda jest mniejsza niż 0 (zero), jest drukowana notka o kompensacie zobowiązań.
- Jeśli kwota salda jest równa kwocie w dokumencie kompensaty, jest drukowana notka o saldzie.

### <a name="set-up-a-vendor-and-a-customer"></a>Konfigurowanie dostawcy i odbiorcy
Firma lub osoba fizyczna może być odbiorcą lub dostawcą Twojej firmy. Opcja kompensaty jest dostępna tylko dla stron powiązanych z Twoją firmą. Aby skonfigurować powiązanie, otwórz szczegóły konta odbiorcy lub dostawcy, a następnie na karcie **Różne** w grupie pól **Przekaz** zaznacz konto powiązanej strony: **Konto odbiorcy** dla głównego dostawcy lub **Konto dostawcy** dla głównego odbiorcy.

### <a name="create-a-compensation-journal"></a>Tworzenie arkusza kompensaty
Opcjonalnie można utworzyć arkusza, który będzie używany do przedstawiania propozycji kompensaty. Można zaksięgować transakcje z propozycji oraz dodatkowo wydrukować raport o kompensacie. Wybierz kolejno opcje **Księga główna** > **Wpisy w arkuszu** > **Arkusze finansowe**.

## <a name="record-transactions"></a>Rejestrowanie transakcji
Zazwyczaj wszystkie faktury zarejestrowane dla skojarzonych kont odbiorców i dostawców są dostępne i mogą być używane do kompensaty: 

 - Faktur sprzedaży (**Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**)
 - Faktury niezależne (**Rozrachunki z odbiorcami** > **Faktury** > **Wszystkie faktury niezależne**)
 - Faktury od dostawców (**Rozrachunki z dostawcami** > **Zamówienia zakupu** > **Wszystkie zamówienia zakupu**)
 - Faktury sprzedaży w projekcie (**Zarządzanie projektami i ich księgowanie** > **Faktury projektu** > **Propozycje faktur projektu**)

W procesie kompensaty można również używać dowolnych otwartych transakcji z dostawcami i odbiorcami. Transakcje te obejmują płatności lub faktury rejestrowane za pomocą arkuszy. 

## <a name="process-a-compensation-letter"></a>Przetwarzanie dokumentu kompensaty
Jeśli masz otwarte transakcje z dostawcami i odbiorcami, można rozpocząć proces kompensaty. Otwórz stronę **Wszyscy odbiorcy** lub **Wszyscy dostawcy**, a następnie kliknij przycisk **Transakcje** i przejrzyj wszystkie transakcje ze stronami. Zaznacz jedną lub więcej otwartych transakcji (transakcje mające saldo większe lub mniejsze niż 0 [zero]). Następnie kliknij przycisk **Kompensata**, a zostanie otwarta **Kompensata transakcji odbiorcy/dostawcy**. Ta strona zawiera dwie siatki: jedną dla transakcji z odbiorcami i jedną dla transakcji z dostawcami. Jedna siatka będzie zawierała wybrane przez Ciebie transakcje. Druga siatka pokaże transakcje dostępne dla kompensaty. Można zaznaczyć jedną lub więcej transakcji do skompensowania. Po zakończeniu wybierania transakcji kliknij przycisk **Utwórz kompensatę**. W wyświetlonym oknie dialogowym można ustawić następujące pola:

 - **Arkusz** — wybierz nazwę, pod jaką ma zostać utworzony nowy arkusz.
 - **Arkusz z numerem partii** — wybierz numer istniejącej partii arkuszy.
 - **Data transakcji** — data transakcji wpisów w arkuszu.
 - **Drukowanie raportu o wynagrodzeniu** — zaznacz tę opcję, aby wydrukować raport, który zostanie wysłany do drugiej strony w celu zaakceptowania.

Jeśli ustawisz wartości jednocześnie w polach **Arkusz** i **Arkusz z numerem partii**, numer ma priorytet. W związku z tym transakcje będą tworzone w tym arkuszu, a nie w nowym arkuszu.

## <a name="process-compensation"></a>Przetwarzanie kompensaty
Gdy utworzysz propozycje kompensaty w arkuszu i propozycja zostanie następnie zaakceptowana przez drugą stronę, można przejść do arkusza finansowego i zaksięgować transakcje w celu zarejestrowania kompensat w księdze głównej. Jeśli trzeba ponownie wydrukować raport o kompensacie, należy kliknąć opcję **Drukuj** > **Dokument kompensaty** na stronie wierszy arkusza finansowego.


## <a name="frequently-asked-questions"></a>Często zadawane pytania
**P: Czy można skompensować transakcje równocześnie dla wielu kont dostawców i odbiorców?**

**O:** Może istnieć relacja przekazu między jednym kontem dostawcy i jednym kontem odbiorcy. W związku z tym jednocześnie można przetwarzać kompensatę tylko między pojedynczymi kontami.

**P: Czy do kompensaty można używać transakcji zagranicznych?**

**O:** Domyślnie funkcja kompensaty jest przeznaczona dla transakcji w walucie krajowej. Można również używać transakcji w walucie obcej. Jednak w arkuszu finansowym należy określić kurs wymiany dla tworzonych transakcji propozycji kompensaty.

**P: Czy funkcja kompensaty jest dostępna dla wszystkich krajów i regionów?**

**O:** Funkcja kompensaty jest dostępna tylko dla firm, które mają podstawowy adres działalności na Węgrzech lub w Polsce.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
---
title: "Konfiguracja kompensacji odbiorców oraz dostawców | Microsoft Docs"
description: "Ten temat zawiera informacje o sposobach wykonywania procesu kompensat na kontach dostawców i odbiorców dla firm, które mają podstawowy adres działalności na Węgrzech lub w Polsce."
author: mrolecki
manager: AnnBe
ms.date: 05-19-2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
keywords: CustTable, CustVendCompensation, VendTable, CustTrans, VendTrans
audience: Application User
ms.reviewer: shylaw
ms.custom: 1691503
ms.search.region: Hungary, Poland
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 716262a2787f312aac758f354a72c7cfd2913dff
ms.openlocfilehash: 4690779974a49d21f21d6df4fc2c8399db9c9e51
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017

---

# Konfiguracja kompensacji odbiorców oraz dostawców
<a id="set-up-customer-and-vendor-compensation" class="xliff"></a>
Ten temat zawiera informacje, które pomogą wykonywać proces kompensat na kontach dostawców i odbiorców dla firm, które mają podstawowy adres działalności na Węgrzech lub w Polsce.

Często użytkownicy w Europie Wschodniej muszą rozliczać kwoty należności i zobowiązań dla firmy, która jest zarejestrowana w systemie równocześnie jako odbiorca i dostawca. Ten proces rozliczania wykorzystuje prawną procedurę znaną jako *kompensata* lub *netowanie* (netting). 

## Włączanie kompensowania
<a id="enabling-compensation" class="xliff"></a>

### Konfigurowanie notek kompensacyjnych
<a id="set-up-compensation-notes" class="xliff"></a>
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

### Konfigurowanie dostawcy i odbiorcy
<a id="set-up-a-vendor-and-a-customer" class="xliff"></a>
Firma lub osoba fizyczna może być odbiorcą lub dostawcą Twojej firmy. Opcja kompensaty jest dostępna tylko dla stron powiązanych z Twoją firmą. Aby skonfigurować powiązanie, otwórz szczegóły konta odbiorcy lub dostawcy, a następnie na karcie **Różne** w grupie pól **Przekaz** zaznacz konto powiązanej strony: **Konto odbiorcy** dla głównego dostawcy lub **Konto dostawcy** dla głównego odbiorcy.

### Tworzenie arkusza kompensaty
<a id="create-a-compensation-journal" class="xliff"></a>
Opcjonalnie można utworzyć arkusza, który będzie używany do przedstawiania propozycji kompensaty. Można zaksięgować transakcje z propozycji oraz dodatkowo wydrukować raport o kompensacie. Wybierz kolejno opcje **Księga główna** > **Wpisy w arkuszu** > **Arkusze finansowe**.

## Rejestrowanie transakcji
<a id="record-transactions" class="xliff"></a>
Zazwyczaj wszystkie faktury zarejestrowane dla skojarzonych kont odbiorców i dostawców są dostępne i mogą być używane do kompensaty: 

 - Faktur sprzedaży (**Rozrachunki z odbiorcami** > **Zamówienia** > **Wszystkie zamówienia sprzedaży**)
 - Faktury niezależne (**Rozrachunki z odbiorcami** > **Faktury** > **Wszystkie faktury niezależne**)
 - Faktury od dostawców (**Rozrachunki z dostawcami** > **Zamówienia zakupu** > **Wszystkie zamówienia zakupu**)
 - Faktury sprzedaży w projekcie (**Zarządzanie projektami i ich księgowanie** > **Faktury projektu** > **Propozycje faktur projektu**)

W procesie kompensaty można również używać dowolnych otwartych transakcji z dostawcami i odbiorcami. Transakcje te obejmują płatności lub faktury rejestrowane za pomocą arkuszy. 

## Przetwarzanie dokumentu kompensaty
<a id="process-a-compensation-letter" class="xliff"></a>
Jeśli masz otwarte transakcje z dostawcami i odbiorcami, można rozpocząć proces kompensaty. Otwórz stronę **Wszyscy odbiorcy** lub **Wszyscy dostawcy**, a następnie kliknij przycisk **Transakcje** i przejrzyj wszystkie transakcje ze stronami. Zaznacz jedną lub więcej otwartych transakcji (transakcje mające saldo większe lub mniejsze niż 0 [zero]). Następnie kliknij przycisk **Kompensata**, a zostanie otwarta **Kompensata transakcji odbiorcy/dostawcy**. Ta strona zawiera dwie siatki: jedną dla transakcji z odbiorcami i jedną dla transakcji z dostawcami. Jedna siatka będzie zawierała wybrane przez Ciebie transakcje. Druga siatka pokaże transakcje dostępne dla kompensaty. Można zaznaczyć jedną lub więcej transakcji do skompensowania. Po zakończeniu wybierania transakcji kliknij przycisk **Utwórz kompensatę**. W wyświetlonym oknie dialogowym można ustawić następujące pola:

 - **Arkusz** — wybierz nazwę, pod jaką ma zostać utworzony nowy arkusz.
 - **Arkusz z numerem partii** — wybierz numer istniejącej partii arkuszy.
 - **Data transakcji** — data transakcji wpisów w arkuszu.
 - **Drukowanie raportu o wynagrodzeniu** — zaznacz tę opcję, aby wydrukować raport, który zostanie wysłany do drugiej strony w celu zaakceptowania.

Jeśli ustawisz wartości jednocześnie w polach **Arkusz** i **Arkusz z numerem partii**, numer ma priorytet. W związku z tym transakcje będą tworzone w tym arkuszu, a nie w nowym arkuszu.

## Przetwarzanie kompensaty
<a id="process-compensation" class="xliff"></a>
Gdy utworzysz propozycje kompensaty w arkuszu i propozycja zostanie następnie zaakceptowana przez drugą stronę, można przejść do arkusza finansowego i zaksięgować transakcje w celu zarejestrowania kompensat w księdze głównej. Jeśli trzeba ponownie wydrukować raport o kompensacie, należy kliknąć opcję **Drukuj** > **Dokument kompensaty** na stronie wierszy arkusza finansowego.


## Często zadawane pytania
<a id="frequently-asked-questions" class="xliff"></a>
**P: Czy można skompensować transakcje równocześnie dla wielu kont dostawców i odbiorców?**

**O:** Może istnieć relacja przekazu między jednym kontem dostawcy i jednym kontem odbiorcy. W związku z tym jednocześnie można przetwarzać kompensatę tylko między pojedynczymi kontami.

**P: Czy do kompensaty można używać transakcji zagranicznych?**

**O:** Domyślnie funkcja kompensaty jest przeznaczona dla transakcji w walucie krajowej. Można również używać transakcji w walucie obcej. Jednak w arkuszu finansowym należy określić kurs wymiany dla tworzonych transakcji propozycji kompensaty.

**P: Czy funkcja kompensaty jest dostępna dla wszystkich krajów i regionów?**

**O:** Funkcja kompensaty jest dostępna tylko dla firm, które mają podstawowy adres działalności na Węgrzech lub w Polsce.


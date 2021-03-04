---
title: Rozwiązywanie problemów dotyczących pobierania i pakowania
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pobierania i pakowania w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 74854fa95837dd8a133860e2a017be4c92ff84a3
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645484"
---
# <a name="troubleshoot-picking-and-packing"></a>Rozwiązywanie problemów dotyczących pobierania i pakowania

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pobierania i pakowania w Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-dimension-location-cant-be-left-blank-if-dimension-serial-number-is-set"></a>Otrzymuję następujący komunikat o błędzie: „Nie można pozostawić pustej lokalizacji wymiaru, jeśli ustawiono numer seryjny wymiaru”.

### <a name="issue-description"></a>Opis problemu

Ten komunikat o błędzie pojawia się, jeśli utworzysz zlecenie przeniesienia dla pozycji seryjnej przy użyciu magazynu, który obsługuje zaawansowane zarządzanie magazynem (WMS), a następnie po zakończeniu pracy spróbujesz potwierdzić wysyłkę.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Pole **Domyślna lokalizacja przychodu** jest puste dla magazynu tranzytowego magazynu „z”. Aby rozwiązać ten problem, należy określić domyślną lokalizację przychodu w magazynie tranzytowym. Upewnij się, że ta lokalizacja jest kontrolowana za pomocą numeru identyfikacyjnego.

## <a name="i-receive-the-following-error-message-invalid-license-plate"></a>Zgłaszany jest następujący komunikat o błędzie: „Nieprawidłowy numer identyfikacyjny".

### <a name="issue-description"></a>Opis problemu

Ten komunikat o błędzie pojawia się w aplikacji magazynowania podczas skanowania identyfikatora numeru identyfikacyjnego.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Upewnij się, że identyfikator numeru identyfikacyjnego znajduje się w tabeli numerów identyfikacyjnych, a pozycje i ilości w numerze identyfikacyjnym są dostępne (innymi słowy, nie są zablokowane).

## <a name="i-receive-the-following-error-message-field-load-weight-1-can-only-contain-positive-numbers-update-has-been-canceled"></a>Otrzymuję następujący komunikat o błędzie: „Pole 'Waga ładunku' (=-%1) może zawierać tylko liczby dodatnie. Aktualizacja została anulowana".

### <a name="issue-description"></a>Opis problemu

Ten komunikat o błędzie jest wyświetlany, jeśli podczas przetwarzania pracy z lokalizacji pakowania do lokalizacji przemieszczania lub z lokalizacji przemieszczania do lokalizacji dokowania jest otwarta praca.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby rozwiązać ten problem, przejdź do **Administrowanie systemem \> Zadania okresowe \> Baza danych \> Sprawdzanie spójności** i uruchom proces **Sprawdzenie spójności wagi ładunku magazynu**.

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a>Otrzymuję następujący komunikat o błędzie: „Ilość jest nieprawidłowa dla jednostki %1”.

### <a name="issue-description"></a>Opis problemu

Ten komunikat o błędzie jest wyświetlany podczas próby przeprowadzenia *dzielenie pobierania* na wielu partiach.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Pracownik magazynu musi skorzystać z procesu *Pobieranie w niedomiarze* w aplikacji magazynu. Jeśli próbujesz pobrać wiele partii z tej samej lokalizacji, możesz również skorzystać z opcji **Pełny** w aplikacji magazynowej.

## <a name="i-cant-move-inventory-to-a-location-that-is-license-platecontrolled"></a>Nie można przenieść zapasów do lokalizacji, kontrolowanej za pomocą numeru identyfikacyjnego.

### <a name="issue-description"></a>Opis problemu

Nie można zredukować ilości pobranych w ładunku.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

We wcześniejszych wersjach nie można zredukować ilości pobranych w ładunku. Można jednak teraz cofnąć wybór lokalizacji kontrolowanej przez numer identyfikacyjny. Należy określić wartość **Lokalizacja** i wartość **Numer identyfikacyjny** dla wiersza ładunku na stronie **Zmniejsz ilość pobraną**.

## <a name="can-i-print-a-delivery-note-or-packing-content-by-warehouse"></a>Czy można wydrukować dokumentdostawy lub zawartość opakowania według magazynu?

### <a name="issue-description"></a>Opis problemu

Chcesz wydrukować dokument dostawy lub zawartość opakowania według magazynu lub oddziału na stronie **Aktualizacja wiersza szablonu audytu pracy**.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Podczas drukowania dokumentu przy użyciu ustawień zarządzania drukowaniem należy ograniczyć zakres (oddział/magazyn), korzystając z funkcji zarządzania drukowaniem, a nie wybierając opcję **Edytuj ustawienia drukowania** na stronie **Aktualizacja wiersza szablonu audytu pracy**.

## <a name="i-cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Nie mogę anulować dokumentu dostawy po zaksięgowaniu go z zamówienia sprzedaży.

### <a name="issue-description"></a>Opis problemu

Po włączeniu procesu pobierania i wysyłania dla modułu WMS nie można anulować dokumentu dostawy po jego zaksięgowaniu z zamówienia sprzedaży.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby poprawić zaksięgowane dokumenty dostawy dla towarów, dla których włączono WMS, księgowanie musi nastąpić z ładunku, a nie z zamówienia. Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Ogólnie rzecz biorąc, zamówienie sprzedaży, które zostało pobrane i wysłane w ramach procesów zarządzania magazynem, może być dokumentem dostawy - aktualizowanym na podstawie ładunku lub wysyłki oraz samego dokumentu zamówienia sprzedaży. Jednak w przypadku dokumentu dostawy zaktualizowanie zamówienia sprzedaży z dokumentu zamówienie sprzedaży, wycofanie dokumentu dostawy nadal nie może zostać wykonane z poziomu załadunku lub zamówienia sprzedaży. Dlatego zalecamy użycie księgowania dokumentu dostawy z ładunku. W takim przypadku wycofanie, które musi zostać wykonane z ładunku, będzie włączone.

## <a name="i-receive-the-following-error-message-not-enough-work-can-be-found-for-cluster"></a>Wyświetlany jest następujący komunikat o błędzie: „Dla grupy nie można znaleźć wystarczającej ilości pracy”.

### <a name="issue-description"></a>Opis problemu

Używając procesu *Pobieranie dla grupy sterowane przez system*, jeśli skonfigurujesz profil grupy, w którym można odebrać na przykład 10 stanowisk, proces działa zgodnie według planu, kiedy jest wystarczająco pracy dla 10 stanowisk odbioru. Jeśli jednak istnieje tylko osiem stanowisk do pobrania, ten komunikat o błędzie jest wyświetlany, ponieważ nie ma wystarczającej ilości pracy dla jednej grupy.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby rozwiązać ten problem, edytuj profil grupy i w opcji **Aktywuj stanowiska** określ wartość *Nie*.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
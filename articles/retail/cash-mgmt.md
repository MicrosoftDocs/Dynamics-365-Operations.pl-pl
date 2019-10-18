---
title: Ulepszenia w zakresie zarządzania gotówką
description: W tym temacie opisano ulepszenia w zakresie zarządzania gotówką w punkcie sprzedaży w programie Dynamics 365 Retail.
author: anpurush
manager: AnnBe
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 49d70a8d983bf3475e01f8fcb80d569b13568485
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019538"
---
# <a name="cash-management-improvements"></a>Ulepszenia w zakresie zarządzania gotówką

[!include [banner](includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Zarządzanie gotówką jest kluczową funkcją dla sprzedawców detalicznych w sklepach fizycznych. Sklepy detaliczne chcą mieć systemy, które zapewnią im pełną identyfikowalność i możliwość rozliczania gotówki i jej przepływów między różnymi kasami i kasjerami w sklepie. Muszą oni być w stanie uzgodnić wszelkie różnice i określić odpowiedzialność.


Microsoft Dynamics 365 Retail ma funkcje zarządzania gotówką w swojej aplikacji punktu sprzedaży. Jednak w wersjach aplikacji Retail starszych niż 10.0.3 funkcje zarządzania gotówką nie są na tyle rozbudowane, aby zapewnić pełną identyfikowalność przepływów gotówki w sklepach. Chociaż sprzedawcy detaliczni mogą uzgodnić gotówkę w sklepie, to nie są w stanie precyzyjnie określić odpowiedzialności w razie rozbieżności ze stanem faktycznym.


W usłudze Retail w wersji 10.0.3 i nowszych sprzedawcy detaliczni zyskują identyfikowalność przepływów gotówki. W ramach tej identyfikowalności sprzedawcy detaliczni będą mogli definiować sejfy, tworzyć dwustronne transakcje kasowe oraz uzgadniać transakcje zarządzania gotówką.

## <a name="set-up-traceability-and-define-safes"></a>Konfigurowanie identyfikowalności i definiowanie sejfów

Aby skonfigurować nową funkcję zarządzania gotówką, należy wykonać następujące kroki w celu skonfigurowania profilu funkcji dla sklepów.

1. Przejdź do opcji **Sprzedaż detaliczna \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji** i wybierz powiązany ze sklepami profil funkcji, dla którego chcesz udostępnić ulepszenia w zakresie zarządzania gotówką.
2. Na skróconej karcie **Funkcje** profilu funkcji, w sekcji **Zaawansowane zarządzanie gotówką**, zmień ustawienie opcji **Włącz identyfikowalność gotówki** na **Tak**.
3. Aby skonfigurować sejfy, przejdź do opcji **Sprzedaż detaliczna \> Kanały \> Sklepy detaliczne \> Wszystkie sklepy detaliczne** i wybierz sklep.
4. Na stronie **Sklepy** w okienku akcji na karcie **Konfiguracja**, w grupie **Konfiguracja** wybierz opcję **Sejfy**. Za pomocą tej opcji można definiować i aktualizować wiele sejfów sklepu.
4. Przed użyciem tej funkcji należy uruchomić zadanie harmonogramu dystrybucji **Konfiguracja kanału 1070** w celu zsynchronizowania tych konfiguracji z bazą danych kanału.

## <a name="additional-cash-management-changes"></a>Dodatkowe zmiany w zakresie zarządzania gotówką

W module Retail w wersji 10.0.3 i nowszych dostępne są ponadto następujące funkcje związane z transakcjami gotówkowymi:

- Użytkownik, któremu jest wyświetlany monit „Zadeklaruj kwotę początkową”, musi wprowadzić źródło gotówki. Użytkownik może wyszukać dostępne sejfy, które są zdefiniowane w sklepie, oraz wybrać sejf, z którego wyjmuje gotówkę, aby włożyć ją do kasy.
- Użytkownik, który wykonuje operację „Pobranie środków płatniczych”, jest monitowany o wybranie na liście otwartych transakcji typu „Przyjęcie do kasy”, transakcji, względem której wykonywana jest operacja. Jeśli w systemie nie istnieje odpowiednie przyjęcie do kasy, użytkownik może utworzyć niepowiązaną transakcję pobrania środków płatniczych.
- W trakcie operacji „Przyjęcie do kasy” użytkownik jest monitowany o wybranie na liście otwartych transakcji „Pobranie środków płatniczych”, transakcji, względem której wykonywana jest operacja przyjęcia do kasy. Jeśli w systemie nie istnieje odpowiednie pobranie środków płatniczych, użytkownik może utworzyć niepowiązaną transakcję przyjęcia do kasy.
- Użytkownik, który wykonuje operację „Przekaż do sejfu”, jest monitowany o wybranie sejfu, do którego przekazuje gotówkę.
- W przypadku sejfów zdefiniowanych w sklepie użytkownicy mogą zarządzać takimi operacjami, jak deklarowanie początkowej kwoty, wykonywać przyjęcie do kasy, wykonywać pobranie środków płatniczych oraz wykonywać wpłatę do banku.
- Użytkownicy mający odpowiednie uprawnienia mogą wykonywać operacje „Zarządzanie zmianami” i wyświetlać salda gotówkowe aktywnych zmian, zawieszonych zmian i zmian z ukryciem raportu.
- Aby uzgodnić transakcje gotówkowe w ramach zmiany lub z różnych zmian, wybierz zmianę do uzgodnienia, a następnie wybierz opcję **Uzgodnij**. Zostanie wyświetlony widok z listą uzgodnionych i nieuzgodnionych transakcji na oddzielnych kartach. W tym widoku użytkownicy mogą wybrać nieuzgodnione transakcje i uzgodnić je, albo wybrać poprzednio uzgodnione transakcje i nie uzgadniać ich.
- W trakcie uzgadniania, jeśli wybrana transakcja nie ma salda, użytkownik musi wprowadzić opis przyczyny niezbilansowania uzgodnienia. Użytkownicy mogą wybrać pojedynczą transakcję i uzgodnić ją z odpowiednim opisem przyczyny w razie potrzeby.
- Użytkownicy mogą kontynuować uzgadnianie i nieuzgadnianie transakcji, aż zmiana zostanie zamknięta. Po zamknięciu zmiany transakcje nie mogą być nieuzgodnione.
- Gdy użytkownik decyduje się na zamknięcie zmiany, moduł Retail sprawdza, czy zmiana nie zawiera żadnych nieuzgodnionych transakcji zarządzania gotówką. Użytkownicy nie mogą zamknąć zmiany, jeśli zawiera nieuzgodnione transakcje.

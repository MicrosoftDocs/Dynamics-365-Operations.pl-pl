---
title: Identyfikowanie i rozwiązywanie konfliktów w podziale obowiązków
description: Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d4a6bd14090213cc19a072d030bc26886c7a8d0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "353110"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identyfikowanie i rozwiązywanie konfliktów w podziale obowiązków

[!include [task guide banner](../../includes/task-guide-banner.md)]

Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników. Ta koncepcja jest nazywana podziałem obowiązków. Gdy definicja roli zabezpieczeń lub przypisanie ról użytkownika naruszają reguły, jest rejestrowany konflikt. Wszystkie konflikty muszą być rozwiązane przez administratora. Aby zidentyfikować i rozwiązać konflikty, wykonaj procedurę opisaną poniżej. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Sprawdzanie, czy przypisania ról użytkowników są zgodne z nowymi regułami podziału obowiązków
1. Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Sprawdź zgodność przypisań ról użytkownika.
2. Kliknij przycisk OK.
    * W powiadomieniu są wyświetlane wyniki sprawdzania poprawności.     Jeśli występuje konflikt, można otworzyć stronę Użytkownicy i zmienić przypisania ról użytkownika. Konflikty są również zapisywane na stronie Konflikty podziału obowiązków.     Aby uruchomić proces weryfikacji jako zadanie wsadowe, zaznacz opcję Przetwarzanie wsadowe, a następnie skonfiguruj parametry tego przetwarzania. Po wykonaniu zadania wsadowego można przejrzeć konflikty na stronie Konflikty podziału obowiązków.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Wyświetlanie i rozwiązywanie konfliktów z przypisaniami ról użytkowników
1. Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Konflikty podziału obowiązków.
    * Wybierz konflikt, a następnie kliknij jeden z poniższych przycisków:     Nie zezwalaj na przypisanie — Odmowa przypisania użytkownika do dodatkowej roli zabezpieczeń. Jeśli nie pozwolisz na automatyczne przypisanie roli, użytkownik jest oznaczany jako wykluczony z roli. Wykluczonemu użytkownikowi nie jest przyznawany dostęp skojarzony z rolą. Użytkownik nie może otrzymać roli, dopóki administrator nie usunie wykluczenia.     Zezwalaj na przypisanie — Zignorowanie konfliktu i pozwolenie na przypisanie użytkownika do obu ról zabezpieczeń. Jeśli zignorujesz konflikt, musisz wprowadzić przyczynę w polu Przyczyna zastąpienia.  
2. Zamknij stronę.
3. Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Nierozwiązane konflikty podziału obowiązków.
    * Wybierz konflikt, a następnie kliknij jeden z poniższych przycisków:     Nie zezwalaj na przypisanie — Odmowa przypisania użytkownika do dodatkowej roli zabezpieczeń. Jeśli nie pozwolisz na automatyczne przypisanie roli, użytkownik jest oznaczany jako wykluczony z roli. Wykluczonemu użytkownikowi nie jest przyznawany dostęp skojarzony z rolą. Użytkownik nie może otrzymać roli, dopóki administrator nie usunie wykluczenia.     Zezwalaj na przypisanie — Zignorowanie konfliktu i pozwolenie na przypisanie użytkownika do obu ról zabezpieczeń. Jeśli zignorujesz konflikt, musisz wprowadzić przyczynę w polu Przyczyna zastąpienia.    
4. Zamknij stronę.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Sprawdzanie, czy istniejące role są zgodne z nowymi regułami podziału obowiązków
1. Wybierz kolejno opcje Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Reguły podziału obowiązków.
    * Wybierz regułę.  
2. Kliknij opcję Sprawdź poprawność obowiązków i ról.
    * Jeśli którakolwiek istniejąca rola narusza wybraną regułę, jest wyświetlany komunikat zawierający nazwę roli oraz nazwy obowiązków powodujących konflikt. Administrator musi wskazać środki minimalizacji ryzyka związanego z zabezpieczeniami lub zmodyfikować rolę, tak aby nie naruszała reguł podziału obowiązków.     Jeśli żadna rola nie narusza wybranej reguły, komunikat wskazuje, że wszystkie role są zgodne.  


---
title: Identyfikowanie i rozwiązywanie konfliktów w podziale obowiązków
description: Ten temat wyjaśnia, jak identyfikować i rozwiązywać konflikty w podziale obowiązków.
author: maertenm
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesConflict, SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c89d27eb8b587e8936258aae3ec1fee4574ccfb
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180928"
---
# <a name="identify-and-resolve-conflicts-in-segregation-of-duties"></a>Identyfikowanie i rozwiązywanie konfliktów w podziale obowiązków

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ten temat wyjaśnia, jak identyfikować i rozwiązywać konflikty w podziale obowiązków. Można ustawić reguły rozdzielania zadań, które mają być wykonywane przez różnych użytkowników. Ta koncepcja jest nazywana podziałem obowiązków. Gdy definicja roli zabezpieczeń lub przypisanie ról użytkownika naruszają reguły, jest rejestrowany konflikt. Wszystkie konflikty muszą być rozwiązane przez administratora. Aby zidentyfikować i rozwiązać konflikty, wykonaj procedurę opisaną poniżej. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF.


## <a name="verify-whether-user-role-assignments-comply-with-new-rules-for-segregation-of-duties"></a>Sprawdzanie, czy przypisania ról użytkowników są zgodne z nowymi regułami podziału obowiązków
1. Wybierz kolejno **okienko nawigacji > Moduły > Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Sprawdź zgodność przypisań ról użytkownika**.
2. Kliknij przycisk **OK**. W powiadomieniu są wyświetlane wyniki sprawdzania poprawności. Jeśli występuje konflikt, można otworzyć stronę **Użytkownicy** i zmienić przypisania ról użytkownika. Konflikty są również zapisywane na stronie **Konflikty podziału obowiązków**. Aby uruchomić proces weryfikacji jako zadanie wsadowe, zaznacz opcję **Przetwarzanie wsadowe**, a następnie skonfiguruj parametry tego przetwarzania. Po wykonaniu zadania wsadowego można przejrzeć konflikty na stronie **Konflikty podziału obowiązków**.  

## <a name="view-and-resolve-conflicting-user-role-assignments"></a>Wyświetlanie i rozwiązywanie konfliktów z przypisaniami ról użytkowników
1. Wybierz kolejno **okienko nawigacji > Moduły > Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Konflikty podziału obowiązków.** Wybierz konflikt, a następnie wybierz jeden z poniższych przycisków: **Nie zezwalaj na przypisanie — Odmowa przypisania użytkownika do dodatkowej roli zabezpieczeń**. Jeśli nie pozwolisz na automatyczne przypisanie roli, użytkownik jest oznaczany jako wykluczony z roli. Wykluczonemu użytkownikowi nie jest przyznawany dostęp skojarzony z rolą. Użytkownik nie może otrzymać roli, dopóki administrator nie usunie wykluczenia. Zezwalaj na przypisanie — **Zignorowanie** konfliktu i pozwolenie na przypisanie użytkownika do obu ról zabezpieczeń. Jeśli zignorujesz konflikt, musisz wprowadzić przyczynę w polu **Przyczyna zastąpienia**.  
2. Zamknij stronę.
3. Wybierz kolejno **okienko nawigacji > Moduły > Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Nierozwiązane konflikty podziału obowiązków.** Wybierz konflikt, a następnie wybierz jeden z poniższych przycisków: **Nie zezwalaj na przypisanie — Odmowa przypisania użytkownika do dodatkowej roli zabezpieczeń**. Jeśli nie pozwolisz na automatyczne przypisanie roli, użytkownik jest oznaczany jako wykluczony z roli. Wykluczonemu użytkownikowi nie jest przyznawany dostęp skojarzony z rolą. Użytkownik nie może otrzymać roli, dopóki administrator nie usunie wykluczenia. Zezwalaj na przypisanie — **Zignorowanie** konfliktu i pozwolenie na przypisanie użytkownika do obu ról zabezpieczeń. Jeśli zignorujesz konflikt, musisz wprowadzić przyczynę w polu **Przyczyna zastąpienia**.    
4. Zamknij stronę.

## <a name="verify-whether-existing-roles-comply-with-new-rules-for-segregation-of-duties"></a>Sprawdzanie, czy istniejące role są zgodne z nowymi regułami podziału obowiązków
1. Wybierz kolejno **okienko nawigacji > Moduły > Administrowanie systemem > Zabezpieczenia > Podział obowiązków > Reguły podziału obowiązków**. Wybierz regułę.  
2. Wybierz **Sprawdź poprawność obowiązków i ról**. Jeśli którakolwiek istniejąca rola narusza wybraną regułę, jest wyświetlany komunikat zawierający nazwę roli oraz nazwy obowiązków powodujących konflikt. Administrator musi wskazać środki minimalizacji ryzyka związanego z zabezpieczeniami lub zmodyfikować rolę, tak aby nie naruszała reguł podziału obowiązków. Jeśli żadna rola nie narusza wybranej reguły, komunikat wskazuje, że wszystkie role są zgodne.  


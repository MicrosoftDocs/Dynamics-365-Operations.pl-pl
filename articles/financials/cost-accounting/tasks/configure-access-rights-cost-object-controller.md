---
title: Konfigurowanie praw dostępu kontrolera obiektów kosztów
description: Ta procedura umożliwia skonfigurowanie uprawnień dostępu kontrolerowi obiektów kosztów.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b7018f9d4926321341af94efd13911e2c69f5f5
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/29/2019
ms.locfileid: "351178"
---
# <a name="configure-access-rights-for-a-cost-object-controller"></a>Konfigurowanie praw dostępu kontrolera obiektów kosztów

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura umożliwia skonfigurowanie uprawnień dostępu kontrolerowi obiektów kosztów. Nagranie wykorzystuje dane firmy demonstracyjnej USP2.


## <a name="assign-the-cost-object-controller-role"></a>Przypisywanie roli kontrolera obiektów kosztów
1. Wybierz kolejno opcje Administrowanie systemem > Użytkownicy > Użytkownicy.
2. Skorzystaj z opcji szybkiego filtrowania, aby znaleźć rekordy. Na przykład wyfiltruj według pola Nazwa użytkownika z wartością „alicia”.
3. Na liście kliknij łącze w wybranym wierszu.
4. Kliknij opcję Przypisz role.
5. Na liście znajdź i zaznacz odpowiedni rekord.
6. Kliknij przycisk OK.

## <a name="enable-access-list-security"></a>Włączanie zabezpieczeń listy dostępu
1. Wybierz kolejno opcje Rachunek kosztów > Wymiary > Hierarchie wymiarów.
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Wybierz opcję Organizacja.  
3. Kliknij przycisk Edytuj.
4. W polu Hierarchia list dostępu wybierz opcję Tak.
5. Kliknij opcję Wyświetl hierarchię.

## <a name="assign-access-rights-to-user"></a>Przypisywanie praw dostępu użytkownikowi
1. Kliknij przycisk Nowy.
2. Na liście oznacz wybrany wiersz.
3. W polu Identyfikator użytkownika wprowadź lub wybierz wartość.
    * Wybierz opcję Administrator.  
4. W drzewie zaznacz element „Organizacja\Dyrektor generalny\Dyrektor finansowy\FIM”.
5. Kliknij przycisk Nowy.
6. Na liście oznacz wybrany wiersz.
7. W polu Identyfikator użytkownika wprowadź lub wybierz wartość.
    * Wybierz opcję Alicia.  
8. Kliknij przycisk Zapisz.

## <a name="enable-access-rights-in-cost-accounting"></a>Włączanie praw dostępu w module Rachunek kosztów
1. Wybierz kolejno opcje Rachunek kosztów > Ustawienia > Parametry.
2. Kliknij kartę Ogólne.
3. Zaznacz opcję Tak w polu Włącz dostęp z prawem do wyświetlania elementów członkowskich wymiaru obiektu kosztów.
4. Kliknij przycisk Zapisz.
5. Zamknij stronę.
6. Wybierz kolejno opcje Rachunek kosztów > Ustawienia > Konfiguracja obszaru roboczego Kontrola kosztów.
7. Kliknij przycisk Edytuj.
8. W polu Opublikowane wybierz opcję Tak.
    * Jeśli wybierzesz opcję Tak, raporty w obszarze roboczym Kontrola kosztów będą mogły być wyświetlane przez użytkownika przypisanego do jednej z następujących czterech ról: Menedżer rachunku kosztów, Księgowy kosztów, Księgowy rachunku kosztów i Kontroler obiektów kosztów. Jeśli wybierzesz opcję Nie, raporty będą mogły być wyświetlane tylko przez użytkowników przypisanych do jednej z następujących czterech ról: Menedżer rachunku kosztów, Księgowy kosztów i Księgowy rachunku kosztów.    
9. Kliknij przycisk Zapisz.


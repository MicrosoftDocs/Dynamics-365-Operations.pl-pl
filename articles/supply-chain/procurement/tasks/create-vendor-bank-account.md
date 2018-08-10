--- 
title: Tworzenie konta bankowego dostawcy
description: "W tej procedurze pokazano sposób tworzenia konta bankowego dla dostawcy."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: adb759c59d7275e7323dbb760de56acdef2e3cff
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-vendor-bank-account"></a>Tworzenie konta bankowego dostawcy

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia konta bankowego dla dostawcy. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.

1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.
2. Zaznacz dostawcę, dla którego chcesz utworzyć konto bankowe, a następnie kliknij łącze identyfikatora konta dostawcy.
3. W okienku akcji kliknij pozycję Dostawca.
4. Kliknij przycisk konta bankowe
5. Kliknij przycisk Nowy.
6. W polu Konto bankowe wpisz wartość.
    * Ten identyfikator będzie używany do identyfikowania konta bankowego w rekordzie dostawcy.  
7. W polu Nazwa wpisz wartość.
8. W polu Grupy bankowe wprowadź lub wybierz wartość.
9. W polu Typ kodu banku wybierz opcję.
    * Jest to typ numeru rozliczeniowego używanego w płatnościach międzynarodowych.  
10. W polu Numer konta bankowego wpisz wartość.
11. W polu Kod SWIFT wpisz wartość.
12. W polu IBAN wpisz wartość.
    * Numer IBAN musi mieć poprawny format. Na przykład można użyć DE89370400440532013000.  
    * Konto bankowe ma stan Aktywny, jeśli osiągnięto datę aktywacji, a nie przekroczono data ważności. Konto jest również aktywne, gdy oba pola — Data aktywacji i Data ważności — są puste. Jeśli daty w obu polach Data aktywacji i Data ważności wypadają w przyszłości, płatności elektroniczne są niedostępne. Inne typy płatności są dostępne i konto bankowe jest aktywne.  
13. Rozwiń sekcję Ustawienia.
14. W polu Kod tekstu wpisz wartość.
    * To pole zawiera kod, który będzie wyświetlany na wyciągu bankowym odbiorcy.  
15. W polu Komunikat do banku wpisz wartość.
16. W polu Odwołanie do kursu wymiany wpisz wartość.
    * Jest to numer referencyjny przyszłego lub stałego kursu wymiany.  
17. W polu Waluta wprowadź lub wybierz wartość.
    * W przypadku wystawiania przelewów testowych ta sekcja zawiera podgląd ich stanu (zatwierdzone lub oczekujące).  
18. Rozwiń sekcję Adres.
19. Rozwiń sekcję Przelewy testowe.
20. Rozwiń sekcję Informacje kontaktowe.
21. W polu Numer telefonu wpisz wartość.
22. Zamknij stronę.
23. Kliknij przycisk Edytuj.
24. Rozwiń sekcję Płatność.
25. W polu Konto bankowe zaznacz właśnie utworzone konto.
26. Kliknij przycisk Zapisz.
    * Adres może być dziedziczony z grupy bankowej (jeśli został tam określony) albo można go dodać w tym polu.  



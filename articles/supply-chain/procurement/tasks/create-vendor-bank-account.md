---
title: Tworzenie konta bankowego dostawcy
description: W tej procedurze pokazano sposób tworzenia konta bankowego dla dostawcy.
author: kamaybac
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, LogisticsPostalAddressSingle
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a2e4aa9121dd295649201ea8f674fb1872cd6f5d5bdaf9c6f1cdc47de580dfe
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730281"
---
# <a name="create-a-vendor-bank-account"></a>Tworzenie konta bankowego dostawcy

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób tworzenia konta bankowego dla dostawcy. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF.

1. Przejdź do **Okienko nawigacji > Moduły > Zaopatrzenie i sourcing > Dostawcy > Wszyscy dostawcy.**
2. Zaznacz dostawcę, dla którego chcesz utworzyć konto bankowe, a następnie kliknij łącze w polu **Identfikator konta dostawcy**.
3. W **okienku akcji** kliknij pozycję **Dostawca**.
4. Kliknij przycisk **konta bankowe**.
5. W **Okienku akcji** kliknij **Nowy**.
6. W polu **Konto bankowe** wpisz wartość. Ten identyfikator będzie używany do identyfikowania konta bankowego w rekordzie dostawcy.  
7. W polu **Nazwa** wpisz wartość.
8. W polu **Grupy bankowe** wprowadź lub wybierz wartość.
9. W polu **Typ kodu banku** wybierz opcję. Jest to typ numeru rozliczeniowego używanego w płatnościach międzynarodowych.  
10. W polu **Numer konta bankowego** wpisz wartość.
11. W polu **Kod SWIFT** wpisz wartość.
12. W polu **IBAN** wpisz wartość.
    - Numer IBAN musi mieć poprawny format. Na przykład można użyć DE89370400440532013000.  
    - Konto bankowe ma stan Aktywny, jeśli osiągnięto datę aktywacji, a nie przekroczono data ważności. Konto jest również aktywne, gdy oba pola — Data aktywacji i Data ważności — są puste. Jeśli daty w obu polach Data aktywacji i Data ważności wypadają w przyszłości, płatności elektroniczne są niedostępne. Inne typy płatności są dostępne i konto bankowe jest aktywne.  
13. Rozwiń sekcję **Ustawienia**.
14. W polu **Kod tekstu** wpisz wartość. To pole zawiera kod, który będzie wyświetlany na wyciągu bankowym odbiorcy.  
15. W polu **Komunikat do banku** wpisz wartość.
16. W polu **Odwołanie do kursu wymiany** wpisz wartość. Jest to numer referencyjny przyszłego lub stałego kursu wymiany.
17. W polu **Waluta** wprowadź lub wybierz wartość. W przypadku wystawiania przelewów testowych ta sekcja zawiera podgląd ich stanu (zatwierdzone lub oczekujące).  
18. Rozwiń sekcję **Adres**.
19. Rozwiń sekcję **Przelewy testowe**.
20. Rozwiń sekcję **Informacje kontaktowe**.
21. W polu **Numer telefonu** wpisz wartość.
22. Zamknij stronę.
23. Kliknij przycisk **Edytuj**.
24. Rozwiń sekcję **Płatność**.
25. W polu **Konto bankowe** zaznacz właśnie utworzone konto.
26. Kliknij przycisk **Zapisz**. Adres może być dziedziczony z grupy bankowej (jeśli został tam określony) albo można go dodać w tym polu.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
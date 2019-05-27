---
title: Definiowanie warunków płatności dostawcy
description: Konfigurowanie warunków płatności dla faktur od odbiorców.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68c69d5be5ccbdfb17fea7c61121cbf26fee48d4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569039"
---
# <a name="define-vendor-payment-terms"></a>Definiowanie warunków płatności dostawcy

[!include [task guide banner](../../includes/task-guide-banner.md)]

Konfigurowanie warunków płatności dla faktur od odbiorców. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Warunki płatności.
2. Kliknij przycisk Nowy.
    * Strona Warunki płatności służy do definiowania sposobu obliczania terminu płatności. Nie jest używana do definiowania sposobu obliczania daty rabatu gotówkowego.  
3. W polu Warunki płatności wpisz wartość.
4. Wypełnij pole Opis.
5. W polu Dni wpisz liczbę.
    * Liczba wprowadzona w tym polu zostanie użyta w celu dodania czasu do terminu płatności lub do końca okresu zidentyfikowanego w metodzie płatności. Na przykład wybranie opcji Netto spowoduje dodanie czasu do terminu płatności. Jeśli zaznaczysz opcję Bieżący miesiąc, w celu obliczenia terminu płatności czas zostanie dodany do ostatniego dnia bieżącego miesiąca.  
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.
8. Wybierz kolejno opcje Rozrachunki z dostawcami > Ustawienia płatności > Rabaty gotówkowe.
9. Kliknij przycisk Nowy.
10. W polu Rabat gotówkowy wprowadź identyfikator.
11. Wypełnij pole Opis.
12. Jeśli dostawca oferuje rabat warstwowy, zaznacz następny rabat gotówkowy, który będzie stosowany po upływie terminu bieżącego rabatu.
13. Zamknij stronę.
14. W polu Dni wpisz liczbę.
    * Ilość wprowadzona w polu Dni będzie używana do obliczania daty rabatu gotówkowego w oparciu o opcję wybraną w polu Netto/Bieżące. Jeśli wybrano opcję Netto, w celu wyznaczenia daty rabatu gotówkowego ilość zostanie dodana do daty faktury. Jeśli wybrano opcję Bieżący miesiąc, w celu wyznaczenia daty rabatu gotówkowego ilość zostanie dodana na końcu bieżącego miesiąca.  
15. W polu Rabat wprowadź wartość procentową rabatu gotówkowego. 
16. Wprowadź konto główne, na którym będzie księgowany rabat gotówkowy faktur dla odbiorców.
17. Wprowadź konto główne, na którym będzie księgowany rabat gotówkowy faktur od dostawców.
    * Jeśli w polu „Konta przeciwstawne rabatów” jest ustawiona opcja Użyj konta głównego dla rabaty dostawcy, będzie używane konto główne.  Jeśli wybierzesz opcję Konta w wierszach faktury, rabat gotówkowy będzie księgowany na kontach środków trwałych/wydatków z wierszy faktury.  
18. Kliknij przycisk Zapisz.


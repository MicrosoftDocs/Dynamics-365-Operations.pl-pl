---
title: Definiowanie warunków płatności dla dostawcy
description: W tym artykule opisano sposób konfigurowania warunków płatności dla faktur od dostawcy.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a676856ed43bf1b78684eac0682e0fdef9c84083
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906479"
---
# <a name="define-vendor-payment-terms"></a>Definiowanie warunków płatności dla dostawcy

[!include [banner](../../includes/banner.md)]

W tym artykule opisano sposób konfigurowania warunków płatności dla faktur od dostawcy. W zadaniu wykorzystano firmę demonstracyjną USMF.

1. Wybierz kolejno **okienko nawigacji > Moduły > Rozrachunki z dostawcami > Ustawienia płatności > Warunki płatności**.
2. Wybierz pozycję **Nowy**. Strona **Warunki płatności** służy do definiowania sposobu obliczania terminu płatności. Nie jest używana do definiowania sposobu obliczania daty rabatu gotówkowego.  
3. W polu **Warunki płatności** wpisz wartość.
4. W polu **Opis** wpisz wartość.
5. W polu **Dni** wpisz liczbę. Liczba wprowadzona w tym polu zostanie użyta w celu dodania czasu do terminu płatności lub do końca okresu zidentyfikowanego w **metodzie płatności**. Na przykład wybranie opcji **Netto** spowoduje dodanie czasu do terminu płatności. Jeśli zaznaczysz opcję **Bieżący miesiąc**, w celu obliczenia terminu płatności czas zostanie dodany do ostatniego dnia bieżącego miesiąca.  
6. Wybierz opcję **Zapisz**.
7. Zamknij stronę.
8. Wybierz kolejno opcje **Rozrachunki z dostawcami > Ustawienia płatności > Rabaty gotówkowe**.
9. Wybierz pozycję **Nowy**.
10. W polu **Rabat gotówkowy** wprowadź identyfikator.
11. W polu **Opis** wpisz wartość.
12. Jeśli dostawca oferuje rabat warstwowy, zaznacz następny rabat gotówkowy, który będzie stosowany po upływie terminu bieżącego rabatu.
13. Zamknij stronę.
14. W polu **Dni** wpisz liczbę. Ilość wprowadzona w polu **Dni** będzie używana do obliczania **daty rabatu gotówkowego** w oparciu o opcję wybraną w polu **Netto/Bieżące**. Jeśli wybrano opcję **Netto**, w celu wyznaczenia daty rabatu gotówkowego ilość zostanie dodana do daty faktury. Jeśli wybrano opcję **Bieżący miesiąc**, w celu wyznaczenia daty rabatu gotówkowego ilość zostanie dodana na końcu bieżącego miesiąca.  
15. W polu **Rabat** wprowadź wartość procentową rabatu gotówkowego. 
16. Wprowadź konto główne, do którego zostanie zaksięgowany rabat gotówkowy dla faktur odbiorcy, a następnie wprowadź konto główne, do którego zostanie zaksięgowany rabat gotówkowy dla faktur od dostawcy. Jeśli w polu **Konta przeciwstawne rabatów** jest ustawiona opcja **Użyj konta głównego dla rabaty dostawcy**, będzie używane konto główne. Jeśli wybierzesz opcję **Konta w wierszach faktury**, rabat gotówkowy będzie księgowany na kontach środków trwałych/wydatków z wierszy faktury.  
17. Wybierz opcję **Zapisz**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

---
title: Znajdowanie przestarzałych wariantów produktów
description: Ta procedura przedstawia, jak znaleźć przestarzałe zwolnione produkty lub warianty produktów i skojarzyć stan cyklu życia produktu z przestarzałymi produktami.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5efd1d471559d320102cd81e4be1ba8c1858f45
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435077"
---
# <a name="find-obsolete-product-variants"></a>Znajdowanie przestarzałych wariantów produktów 

[!include [banner](../../includes/banner.md)]

Ta procedura przedstawia, jak znaleźć przestarzałe zwolnione produkty lub warianty produktów i skojarzyć stan cyklu życia produktu z przestarzałymi produktami. Warunek wstępny: przed przystąpieniem do procedury opisanej w tym przewodniku zadania należy zdefiniować co najmniej jeden stan cyklu życia produktu nieaktywny dla planowania.


## <a name="run-a-simulation"></a>Uruchamianie symulacji
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Zadania okresowe > Zmiana stanu cyklu życia dla produktów przestarzałych.
2. W polu Stan cyklu życia nowego produktu wprowadź lub wybierz wartość.
3. W polu Uruchom symulację bez aktualizowania danych produktów zaznacz opcję Tak.
4. W polu Wyklucz produkty utworzone w ciągu tej liczby dni wprowadź liczbę.
5. W polu Wyklucz produkty użyte w transakcjach (w ciągu tej liczby dni) wprowadź liczbę.
6. Rozwiń sekcję Rekordy do uwzględnienia.
7. Kliknij przycisk Filtr.
8. Na liście oznacz wybrany wiersz.
9. W polu Kryteria wpisz wartość.
10. Kliknij przycisk OK.
11. Kliknij przycisk OK.

> [!NOTE]
> Jeśli wyszukiwanie obejmie dużą liczbę produktów, zaleca się uruchamianie symulacji partiami. Nie należy również uruchamiać symulacji w okresie największej aktywności w firmie.  

## <a name="review-the-simulation-results"></a>Przegląd wyników symulacji
1. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Zapytania i raporty > Historia obsługi stanu cyklu życia produktów.
   
> [!NOTE]
> Na tej stronie można również sprawdzić, jak wyświetlić wyniki symulacji i ocenić, ile produktów i wariantów produktów będzie skojarzonych z nowym stanem cyklu życia produktu po uruchomieniu aktualizacji bez symulacji.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>Uruchamianie aktualizacji stanu cyklu życia produktu dla produktów przestarzałych
1. Zamknij stronę.
2. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Zadania okresowe > Zmiana stanu cyklu życia dla produktów przestarzałych.
3. Rozwiń sekcję Rekordy do uwzględnienia.

> [!NOTE]
> Należy zauważyć, że ostatni wybór został zapisany.  

4. W polu Uruchom symulację bez aktualizowania danych produktów zaznacz opcję Nie.
5. Rozwiń sekcję Uruchom w tle.

> [!NOTE]
> W zależności od liczby produktów i wariantów produktów, których dotyczy operacja, należy rozważyć uruchamianie zadania partiami. Nie należy uruchamiać dużego zadania aktualizacji w okresie największej aktywności w firmie.  

6. Kliknij przycisk OK.
7. Wybierz kolejno opcje Zarządzanie informacjami o produktach > Zapytania i raporty > Historia obsługi stanu cyklu życia produktów.

> [!NOTE]
> Sprawdź zwolnione produkty i warianty produktów, które zostały zmienione.  

8. Na liście znajdź i zaznacz odpowiedni rekord.


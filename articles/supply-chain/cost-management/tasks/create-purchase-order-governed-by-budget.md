---
title: Tworzenie zamówienia zakupu regulowanego budżetem
description: Ta procedura służy do tworzenia zamówienia zakupu sprawdzanego pod kątem dostępnego budżetu.
author: ShylaThompson
manager: tfehr
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cbfbbef3bd7c7398f0f17b6cddbbff8c4755638d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963720"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Tworzenie zamówienia zakupu regulowanego budżetem

[!include [banner](../../includes/banner.md)]

Ta procedura służy do tworzenia zamówienia zakupu sprawdzanego pod kątem dostępnego budżetu. Nagranie wykorzystuje dane firmy demonstracyjnej USMF.


## <a name="review-the-budget-control-configuration"></a>Przeglądanie konfiguracji kontroli budżetu
1. Wybierz kolejno opcje Budżetowanie > Ustawienia > Kontrola budżetu > Konfiguracja kontroli budżetu.
2. Kliknij kartę Dostępne środki budżetowe.
3. Kliknij kartę Dokumenty i arkusze.
4. Kliknij kartę Definiowanie reguł kontroli budżetu.
5. Kliknij kartę Zdefiniuj grupy budżetu.
6. Zamknij stronę.

## <a name="create-the-purchase-order-header"></a>Tworzenie nagłówka zamówienia zakupu
1. Wybierz kolejno opcje Zaopatrzenie i sourcing > Zamówienia zakupu > Wszystkie zamówienia zakupu.
2. Kliknij przycisk Nowy.
3. W polu Konto dostawcy wprowadź lub wybierz wartość.
4. Rozwiń sekcję Ogólne.
5. W polu Data księgowania ustaw datę „2016-01-01”.
6. Kliknij przycisk OK.

## <a name="add-a-purchase-order-line"></a>Dodawanie wiersza zamówienia zakupu
1. W polu Kategoria zaopatrzenia wprowadź lub wybierz wartość.
2. Ustaw ilość na 2.
3. W polu Jednostka wprowadź lub wybierz wartość.
4. Ustaw cenę jednostkowa na „10000”.
5. Kliknij opcję Finanse.
6. Kliknij opcję Rozdziel kwoty.
7. W polu Konto księgowe wpisz wartość „601300-001-023--”.
8. Zamknij stronę.

## <a name="perform-budget-checking"></a>Wykonaj kontrolę budżetu
1. Kliknij opcję Finanse.
2. Kliknij opcję Wykonaj kontrolę budżetu.
3. Kliknij opcję Finanse.
4. Kliknij opcję Błędy lub ostrzeżenia dotyczące sprawdzania budżetu.
5. Kliknij przycisk Zamknij.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
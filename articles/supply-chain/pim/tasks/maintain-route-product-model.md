---
title: Obsługa marszruty modelu produktu
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13bbdc706280317c5a1ab7fb21c9585f1c7d48ad
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247797"
---
# <a name="maintain-route-for-a-product-model"></a>Obsługa marszruty modelu produktu

[!include [banner](../../includes/banner.md)]

Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu. Ta procedura wykorzystuje w kolejnych krokach model Głośnik o wysokiej jakości zdefiniowany w firmie demonstracyjnej USMF.


## <a name="add-a-route-operation"></a>Dodawanie operacji marszruty
1. Kliknij opcję Definicja modelu wariantu produktu.
2. Kliknij opcję Modele konfiguracji produktu.
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * Do tego ćwiczenia wybierz model Głośnik o wysokiej jakości.  
4. Na liście kliknij łącze w wybranym wierszu.
5. Rozwiń sekcję Operacje marszruty.
6. Kliknij przycisk Dodaj.
7. W polu Nazwa wpisz wartość.
8. Wypełnij pole Opis.
9. Kliknij przycisk Zapisz.

## <a name="enter-route-operation-details"></a>Wprowadzanie szczegółów operacji marszruty
1. Kliknij opcję Szczegóły operacji marszruty.
2. W polu Operacja wprowadź lub wybierz wartość.
3. W polu Nr operacji Nr wpisz liczbę.
    * Numery operacji decydują o kolejności czynności w marszrucie.  
    * Każda właściwość operacji marszruty może przybierać wartość statyczną lub być zmapowana do atrybutu. Mapowanie do atrybutu spowoduje ustawianie wartość w trakcie konfigurowania.  
4. W polu Grupa marszruty wpisz lub wprowadź wartość.
    * Grupa marszrut określa podstawowe zachowania dotyczące wyceny, zużycia i konfiguracji.  
5. Kliknij kartę Ustawienia.
6. Kliknij kartę Czasy.
7. W polu Ilość z procesu wpisz liczbę.
    * Określ, ile będzie przetwarzanych w jednej operacji.  
8. W polu Godziny/czas wpisz liczbę.
    * Wprowadź współczynnik czasu.  
9. Zaznacz pole wyboru Ustaw.
10. W polu Czas procesu wpisz liczbę.
    * Określ czas przetwarzania dla podanej ilości.  
11. Kliknij kartę Zapotrzebowanie na zasoby.
12. Kliknij przycisk Dodaj.
13. Na liście oznacz wybrany wiersz.
14. W polu Typ wymagania wybierz opcję.
    * Zdecyduj, czy chcesz określić konkretne zasoby czy możliwości, które muszą posiadać.  
15. W polu Zapotrzebowanie wprowadź lub wybierz wartość.
16. Kliknij przycisk OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
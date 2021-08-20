---
title: Obsługa marszruty modelu produktu
description: Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, PCRouteOperationDetails, WrkCtrCapabilityLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 704a6b72c9eb8dc49ba9410ccd3689ba5ccfdd1f03e538b95ad174f6c1ee9796
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746143"
---
# <a name="maintain-route-for-a-product-model"></a>Obsługa marszruty modelu produktu

[!include [banner](../../includes/banner.md)]

Wykonanie tej procedury wymaga istnienia modelu konfiguracji produktu. Ta procedura wykorzystuje w kolejnych krokach model Głośnik o wysokiej jakości zdefiniowany w firmie demonstracyjnej USMF.

## <a name="add-a-route-operation"></a>Dodawanie operacji marszruty

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Na liście znajdź i zaznacz odpowiedni rekord.
    * Do tego ćwiczenia wybierz model Głośnik o wysokiej jakości.  
1. Na liście wybierz łącze w wybranym wierszu.
1. Rozwiń sekcję **Operacje marszruty**.
1. Wybierz opcję **Dodaj**.
1. W polu **Nazwa** wpisz wartość.
1. W polu **Opis** wpisz wartość.
1. Wybierz opcję **Zapisz**.

## <a name="enter-route-operation-details"></a>Wprowadzanie szczegółów operacji marszruty

1. Wybierz opcję **Szczegóły operacji marszruty**.
1. W polu **Operacja** wprowadź lub wybierz wartość.
1. W polu **Nr operacji** wpisz liczbę.
    * Numery operacji decydują o kolejności czynności w marszrucie.  
    * Każda właściwość operacji marszruty może przybierać wartość statyczną lub być zmapowana do atrybutu. Mapowanie do atrybutu spowoduje ustawianie wartość w trakcie konfigurowania.  
1. W polu **Grupa marszruty** wpisz lub wprowadź wartość.
    * Grupa marszrut określa podstawowe zachowania dotyczące wyceny, zużycia i konfiguracji.  
1. Kliknij kartę **Konfiguracja**.
1. Kliknij kartę **Czasy**.
1. W polu **Ilość z procesu** wpisz liczbę.
    * Określ, ile będzie przetwarzanych w jednej operacji.  
1. W polu **Godziny/czas** wpisz liczbę.
    * Wprowadź współczynnik czasu.  
1. Zaznacz pole wyboru **Ustaw**.
1. W polu **Czas procesu** wpisz liczbę.
    * Określ czas przetwarzania dla podanej ilości.  
1. Kliknij kartę **Zapotrzebowanie na zasoby**.
1. Wybierz opcję **Dodaj**.
1. Na liście oznacz wybrany wiersz.
1. W polu **Typ wymagania** wybierz opcję.
    * Zdecyduj, czy chcesz określić konkretne zasoby czy możliwości, które muszą posiadać.  
1. W polu **Zapotrzebowanie** wprowadź lub wybierz wartość.
1. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
---
title: Tworzenie kryteriów wyboru ceny sprzedaży
description: Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47ea7ea2093c540a88d9fd7249b470009c7595d40e2a727d8fcd3bb4b5d74bac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750083"
---
# <a name="create-sales-price-selection-criteria"></a>Tworzenie kryteriów wyboru ceny sprzedaży

[!include [banner](../../includes/banner.md)]

Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach. Procedura wymaga dostępności co najmniej jednego modelu ceny sprzedaży. W tym przykładzie jest używany model ceny będący modelem cen sprzedaży rozwiązania Głośnik w firmie demonstracyjnej USMF. Zazwyczaj procedurę wykonuje menedżer produktu.

## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Dodawanie nowego kryterium dla istniejącego modelu ceny sprzedaży

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Na liście zaznacz wiersz modelu produktu rozwiązania Głośnika, ale nie wybieraj łącza z nazwą modelu.
1. W okienku akcji kliknij pozycję **Model**.
1. Wybierz opcję **Kryteria modelu ceny**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa** wpisz „Grupa odbiorców 10”.
    * Nazwa kryterium modelu ceny służy do identyfikowania bazowych kryteriów wyboru.  
1. Wprowadź lub wybierz wartość w polu **Model ceny**.
1. W polu **Typ zamówienia** zaznacz opcję *Zamówienie sprzedaży*.
    * Typ zamówienia określa pola bazy danych, które będą dostępne dla kwerendy wyboru.  
1. W polu **Obowiązuje od** wpisz datę.
1. W polu **Data ważności** wprowadź datę.
1. Wybierz opcję **Zapisz**.

## <a name="create-the-query-for-the-selection-criteria"></a>Tworzenie zapytania dla kryteriów wyboru

1. Wybierz opcję **Edycja**.
2. W polu **Tabela** wybierz opcję *Odbiorcy*.
3. W polu **Pole** wybierz opcję *Grupa odbiorców*.
    * W tym przykładzie jako kryteriów wyboru użyjemy określonej grupy odbiorców.  
4. W polu **Kryteria** wybierz opcję *Grupa odbiorców 10*.
5. Kliknij przycisk **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
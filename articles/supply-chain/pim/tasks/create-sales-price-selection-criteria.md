---
title: Tworzenie kryteriów wyboru ceny sprzedaży
description: Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ed7083f289948033782f74dd9ed1b3c2d2a73aea
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568454"
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
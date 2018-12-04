--- 
title: "Tworzenie kryteriów wyboru ceny sprzedaży"
description: "Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelSelectionCriteria, SysQueryForm, SysQueryTableLookUp, SysQueryFieldLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 59f6a4131f6a27c0089a1259e3f849f91a47bc87
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-sales-price-selection-criteria"></a>Tworzenie kryteriów wyboru ceny sprzedaży

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach. Procedura wymaga dostępności co najmniej jednego modelu ceny sprzedaży. W tym przykładzie jest używany model ceny będący modelem cen sprzedaży rozwiązania Głośnik w firmie demonstracyjnej USMF. Zazwyczaj procedurę wykonuje menedżer produktu.


## <a name="add-a-new-criterion-for-an-existing-sales-price-model"></a>Dodawanie nowego kryterium dla istniejącego modelu ceny sprzedaży
1. Kliknij opcję Definicja modelu wariantu produktu.
2. Kliknij opcję Modele konfiguracji produktu.
3. Na liście zaznacz wiersz modelu produktu rozwiązania Głośnika, ale nie klikaj łącza z nazwą modelu.
4. W okienku akcji kliknij pozycję Model.
5. Kliknij opcję Kryteria modelu ceny.
6. Kliknij przycisk Nowy.
7. W polu Nazwa wpisz „Grupa odbiorców 10”.
    * Nazwa kryterium modelu ceny służy do identyfikowania bazowych kryteriów wyboru.  
8. Wprowadź lub wybierz wartość w polu Model ceny.
9. W polu Typ zamówienia zaznacz opcję Zamówienie sprzedaży.
    * Typ zamówienia określa pola bazy danych, które będą dostępne dla kwerendy wyboru.  
10. W polu Obowiązuje od wpisz datę.
11. W polu Data ważności wprowadź datę.
12. Kliknij przycisk Zapisz.

## <a name="create-the-query-for-the-selection-criteria"></a>Tworzenie zapytania dla kryteriów wyboru
1. Kliknij przycisk Edytuj.
2. W polu Tabela wybierz opcję Odbiorcy. 
3. W polu Pole wybierz opcję Grupa odbiorców.
    * W tym przykładzie jako kryteriów wyboru użyjemy określonej grupy odbiorców.  
4. W polu Kryteria wybierz opcję Grupa odbiorców 10. 
5. Kliknij przycisk OK.



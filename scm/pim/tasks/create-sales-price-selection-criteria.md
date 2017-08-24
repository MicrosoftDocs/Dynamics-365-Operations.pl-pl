--- 
title: "Tworzenie kryteriów wyboru ceny sprzedaży"
description: "Ta procedura pokazuje, jak utworzyć kryterium wyboru ceny sprzedaży dla modeli ceny sprzedaży opartych na atrybutach."
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 633628e6250baa74df544e814ce6e9656a2f0b06
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="create-sales-price-selection-criteria"></a>Tworzenie kryteriów wyboru ceny sprzedaży

[!include[task guide banner](../../includes/task-guide-banner.md)]

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



---
title: Konfigurowanie i używanie kodów PKWiU dla Polski
description: W tym temacie omówiono konfigurowanie kod PKWiU dla Polski.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Poland
ms.author: v-elgolu
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 93eae39701cd4d909b68e23dc1f5f4d6a63bf437
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852437"
---
# <a name="set-up-and-use-pkwiu-codes"></a>Konfigurowanie i używanie kodów PKWiU

[!include [banner](../includes/banner.md)]

Kod PKWiU jest używany do celów podatkowych w klasyfikacji towarów i usług sprzedawanych w Polsce. Jest on uwzględniony na wszystkich fakturach zamówień sprzedaży, fakturach niezależnych oraz fakturach zaksięgowanych z poziomu modułu Projekt. Za pomocą formularza **Arkusze faktur** można wyświetlić kod PKWiU na fakturze za projekt oraz wydrukować fakturę za projekt. Można również skonfigurować powiadamianie o braku kodu PKWiU na fakturze.

Aby zapewnić, że użytkownicy uwzględniają kod PKWiU na wszystkich fakturach, wybierz jedną z następujących opcji w polu **Wymagany kod PKWiU** na stronie **Parametry modułu rozrachunków z odbiorcami**: 
- **Brak** — nie jest wyświetlany komunikat o braku kodu PKWiU z zamówienia sprzedaży lub faktury niezależnej. Kod PKWiU nie jest wymagany w przypadku faktur. 
- **Ostrzeżenie** — wyświetlanie komunikatu podczas fakturowania zamówienia sprzedaży lub faktury niezależnej, na których brak kod PKWiU. 
- **Błąd** — umożliwia wyświetlenie komunikatu podczas fakturowania zamówienia sprzedaży lub faktury niezależnej, na których brak kodu PKWiU i powoduje zatrzymanie fakturowania. 

## <a name="assign-a-pkwiu-code-to-the-sales-category-hierarchy"></a>Przypisanie kodu PKWiU do hierarchii kategorii sprzedaży

Hierarchie kategorii są używane do klasyfikowania produktów czy transakcji dla celów raportowania i analiz. Hierarchia kategorii o typie Hierarchia kategorii sprzedaży jest używana do organizowania produktów dla działań dotyczących sprzedaży. Można przypisać kod PKWiU do hierarchii kategorii sprzedaży w taki sposób, aby kod PKWiU był uwzględniony na fakturach, które zawierają towary nie zinwentaryzowane. 

1. Kliknij kolejno opcje **Zarządzanie informacjami o produktach** > **Ustawienia** > **Kategorie i atrybuty** > **Hierarchie kategorii**. 
2. Wybierz hierarchię kategorii sprzedaży. W okienku akcji kliknij przycisk **Edytuj**. 
3. Na skróconej karcie **Przypisz kod PKWiU** wprowadź kod PKWiU dla hierarchii kategorii sprzedaży. 

## <a name="assign-a-pkwiu-code-to-released-products"></a>Przypisz kod PKWiU do zwolnionych produktów

1. Kliknij kolejno **Zarządzanie informacjami o produktach** > **Wspólne** > **Zwolnione produkty**. 
2. Wybierz zwolniony produkt, do którego chcesz przypisać kod PKWiU. W okienku akcji kliknij przycisk **Edytuj**. 
3. Na skróconej karcie **Sprzedaż** wprowadź kod PKWiU dla zwolnionego produktu. 

---
title: Ponowne wykorzystywanie konfiguracji produktów
description: Możesz określić, że chcesz automatycznie ponownie używać istniejącej konfiguracji produktu. Wtedy gdy użytkownik zakończy sesję konfiguracji, system sprawdzi, czy już istnieje konfiguracja odpowiadająca opcjom wybranym przez użytkownika. Jeśli znajdzie pasującą konfigurację, ponownie wykorzysta identyfikator konfiguracji, odnośną listę składową (BOM) i marszrutę.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f72d93600db3d9bf0a44ac1fe84111527bb31d0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209415"
---
# <a name="reuse-product-configurations"></a>Ponowne wykorzystywanie konfiguracji produktów

[!include [banner](../includes/banner.md)]

Możesz określić, że chcesz automatycznie ponownie używać istniejącej konfiguracji produktu. Wtedy gdy użytkownik zakończy sesję konfiguracji, system sprawdzi, czy już istnieje konfiguracja odpowiadająca opcjom wybranym przez użytkownika. Jeśli znajdzie pasującą konfigurację, ponownie wykorzysta identyfikator konfiguracji, odnośną listę składową (BOM) i marszrutę.

<a name="requirements-for-reusing-configurations"></a>Wymagania dotyczące ponownego wykorzystywania konfiguracji
---------------------------------------

Aby umożliwić ponowne wykorzystywanie konfiguracji, należy określić następujące informacje dotyczące składników i atrybutów na stronie **Szczegóły modelu konfiguracji produktu**:

-   **Składniki i składniki podrzędne** — Na skróconej karcie **Ogólne** w polu **Użyj ponownie konfiguracji** zaznacz wartość **Tak**.
-   **Atrybuty** — Na skróconej karcie **Atrybuty** zaznacz opcję **Uwzględnij w ponownym użyciu**. Ta opcja jest wyświetlana tylko wtedy, gdy odnośny składnik jest włączony do ponownego wykorzystania. Jeśli nie wybierzesz żadnych atrybutów do ponownego wykorzystania, konfiguracja jest zawsze używana ponownie, niezależnie od opcji wybranych przez użytkownika podczas sesji konfiguracji. Wartości atrybutów w istniejącej konfiguracji muszą odpowiadać opcjom wybranym przez użytkownika. Na przykład jeśli użytkownik wybierze **Niebieski** jako kolor w trakcie sesji konfiguracji, system zweryfikuje, czy istniejąca konfiguracja składnika ma kolor niebieski.

## <a name="resetting-configuration-reuse"></a>Resetowanie ponownego wykorzystywania konfiguracji
Po zresetowaniu funkcji ponownego wykorzystywania konfiguracji wcześniej utworzone konfiguracje nie są już brane pod uwagę. Funkcję można resetować na przykład w sytuacji, gdy zmieniła się specyfikacja BOM lub marszruta, ale powiązane atrybuty nie uległy zmianie. Resetowanie ponownego używania konfiguracji odbywa się skróconej karcie **Ogólne** dla składnika.




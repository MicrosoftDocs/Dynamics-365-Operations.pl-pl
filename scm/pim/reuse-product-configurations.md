---
title: "Ponowne wykorzystywanie konfiguracji produktów"
description: "Możesz określić, że chcesz automatycznie ponownie używać istniejącej konfiguracji produktu. Wtedy gdy użytkownik zakończy sesję konfiguracji, system sprawdzi, czy już istnieje konfiguracja odpowiadająca opcjom wybranym przez użytkownika. Jeśli znajdzie pasującą konfigurację, ponownie wykorzysta identyfikator konfiguracji, odnośną listę składową (BOM) i marszrutę."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 6d5e4988f123bfd70de0b54bf4dc75c4e32c0565
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="reuse-product-configurations"></a>Ponowne wykorzystywanie konfiguracji produktów

[!include[banner](../includes/banner.md)]


Możesz określić, że chcesz automatycznie ponownie używać istniejącej konfiguracji produktu. Wtedy gdy użytkownik zakończy sesję konfiguracji, system sprawdzi, czy już istnieje konfiguracja odpowiadająca opcjom wybranym przez użytkownika. Jeśli znajdzie pasującą konfigurację, ponownie wykorzysta identyfikator konfiguracji, odnośną listę składową (BOM) i marszrutę.

<a name="requirements-for-reusing-configurations"></a>Wymagania dotyczące ponownego wykorzystywania konfiguracji
---------------------------------------

Aby umożliwić ponowne wykorzystywanie konfiguracji, należy określić następujące informacje dotyczące składników i atrybutów na stronie **Szczegóły modelu konfiguracji produktu**:

-   **Składniki i składniki podrzędne** — Na skróconej karcie **Ogólne** w polu **Użyj ponownie konfiguracji** zaznacz wartość **Tak**.
-   **Atrybuty** — Na skróconej karcie **Atrybuty** zaznacz opcję **Uwzględnij w ponownym użyciu**. Ta opcja jest wyświetlana tylko wtedy, gdy odnośny składnik jest włączony do ponownego wykorzystania. Jeśli nie wybierzesz żadnych atrybutów do ponownego wykorzystania, konfiguracja jest zawsze używana ponownie, niezależnie od opcji wybranych przez użytkownika podczas sesji konfiguracji. Wartości atrybutów w istniejącej konfiguracji muszą odpowiadać opcjom wybranym przez użytkownika. Na przykład jeśli użytkownik wybierze **Niebieski** jako kolor w trakcie sesji konfiguracji, system zweryfikuje, czy istniejąca konfiguracja składnika ma kolor niebieski.

## <a name="resetting-configuration-reuse"></a>Resetowanie ponownego wykorzystywania konfiguracji
Po zresetowaniu funkcji ponownego wykorzystywania konfiguracji wcześniej utworzone konfiguracje nie są już brane pod uwagę. Funkcję można resetować na przykład w sytuacji, gdy zmieniła się specyfikacja BOM lub marszruta, ale powiązane atrybuty nie uległy zmianie. Resetowanie ponownego używania konfiguracji odbywa się skróconej karcie **Ogólne** dla składnika.





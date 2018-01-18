---
title: "Wstrzymania zamówień"
description: "W tym temacie opisano, jak wstrzymuje się zamówienia przy użyciu programu Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCRHoldCodeTable, MCRSalesTableOrderHistory, MCRHoldCodeTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 8b4c8ecbef1dc667d3b60411a53f0c63686529c2
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="order-holds"></a>Wstrzymania zamówień

[!include[banner](includes/banner.md)]


W tym temacie opisano, jak wstrzymuje się zamówienia przy użyciu programu Dynamics 365 for Retail.

Zamówienie może zostać wstrzymane z różnych przyczyn. Można na przykład wstrzymać zamówienie, dopóki nie zostaną sprawdzone metody płatności lub adres odbiorcy lub dopóki menedżer nie sprawdzi limitu kredytu odbiorcy. Podczas procesu sprzedaży zdarza się, że zamówienie sprzedaży musi być wstrzymane. Na przykład zamówienie sprzedaży może być wstrzymane z powodu problemów z płatnością, podejrzenia oszustwa lub oczekiwania na przegląd przez menedżera. Gdy zamówienie sprzedaży jest wstrzymane, kod wstrzymania zamówienia zostaje przypisany do zamówienia sprzedaży, aby wskazać przyczynę wstrzymania. Kody wstrzymania zamówień są konfigurowane w oknie **Sprzedaż i marketing** &gt; **Ustawienia** &gt; **Zamówienia sprzedaży** &gt; **Kody wstrzymania zamówień**. Zamówienie sprzedaży może być wstrzymywane ręcznie w chwili utworzenia zamówienia lub później. Oprócz tego zamówienie można wstrzymać automatycznie na podstawie reguł dotyczących oszustw. Gdy zamówienie sprzedaży jest wstrzymane, konieczne może być zaktualizowanie go o dodatkowe informacje. Można również sprawdzić zamówienie sprzedaży podczas kontynuowania pracy nad nim. Zamówienie sprzedaży można wyewidencjonować, ponownie zaewidencjonować, a nawet zastąpić wyewidencjonowanie go przez innego użytkownika. Służy do tego pulpit wstrzymywania zamówień (**Handel detaliczny** &gt; **Odbiorcy** &gt; **Wstrzymania zamówień**). Gdy zamówienie jest gotowe do wykonania, należy usunąć wstrzymanie przed zakończeniem procesu zamówienia.





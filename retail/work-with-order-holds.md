---
title: "Wstrzymania zamówień"
description: "W tym temacie opisano, jak wstrzymuje się zamówienia przy użyciu modułu Handel detaliczny i inny w systemie Dynamics AX."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79132
ms.assetid: 7c00dc35-73e5-400a-8587-22f37ddfc0e0
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 1cb18e3275b8dcdf0a61531ee056995f6e8fbc8d
ms.lasthandoff: 03/31/2017


---

# <a name="order-holds"></a>Wstrzymania zamówień

W tym temacie opisano, jak wstrzymuje się zamówienia przy użyciu modułu Handel detaliczny i inny w systemie Dynamics AX.

Zamówienie może zostać wstrzymane z różnych przyczyn. Można na przykład wstrzymać zamówienie, dopóki nie zostaną sprawdzone metody płatności lub adres odbiorcy lub dopóki menedżer nie sprawdzi limitu kredytu odbiorcy. Podczas procesu sprzedaży zdarza się, że zamówienie sprzedaży musi być wstrzymane. Na przykład zamówienie sprzedaży może być wstrzymane z powodu problemów z płatnością, podejrzenia oszustwa lub oczekiwania na przegląd przez menedżera. Gdy zamówienie sprzedaży jest wstrzymane, kod wstrzymania zamówienia zostaje przypisany do zamówienia sprzedaży, aby wskazać przyczynę wstrzymania. Kody blokady zamówienia sprzedaży są konfigurowane na **sprzedaży i marketingu**&gt;**instalacji**&gt;**zamówienia sprzedaży**&gt;**zamówienia zawiera kody**. Zamówienie sprzedaży może być wstrzymywane ręcznie w chwili utworzenia zamówienia lub później. Oprócz tego zamówienie można wstrzymać automatycznie na podstawie reguł dotyczących oszustw. Gdy zamówienie sprzedaży jest wstrzymane, konieczne może być zaktualizowanie go o dodatkowe informacje. Można również sprawdzić zamówienie sprzedaży podczas kontynuowania pracy nad nim. Możesz sprawdzić zamówienie sprzedaży, sprawdź go ponownie, a nawet override wyewidencjonowanie innego użytkownika za pomocą kolejności przytrzymaj workbench (**sieci sprzedaży i handlu**&gt;**klienci**&gt;**zamówienia posiada**). Gdy zamówienie jest gotowe do wykonania, należy usunąć wstrzymanie przed zakończeniem procesu zamówienia.



---
title: "Wymiary finansowe i konta główne w języku z pisownią od prawej do lewej"
description: "W tym temacie opisano niektóre decyzje wdrożeniowe, które należy podjąć w przypadku używania języka z pisownią od prawej do lewej w programie Microsoft Dynamics 365 for Operations, gdy trzeba skonfigurować wymiary finansowe i konta główne."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0a2fcbbc91960e0602f42d89ca5e46b8d51f98d6
ms.openlocfilehash: da5c53ddf113daf19a9832cf59f7a231a00b3367
ms.lasthandoff: 03/31/2017


---

# <a name="financial-dimensions-and-main-accounts-in-a-right-to-left-language"></a>Wymiary finansowe i konta główne w języku z pisownią od prawej do lewej

W tym temacie opisano niektóre decyzje wdrożeniowe, które należy podjąć w przypadku używania języka z pisownią od prawej do lewej w programie Microsoft Dynamics 365 for Operations, gdy trzeba skonfigurować wymiary finansowe i konta główne.

Wymiary finansowe i konta główne są kluczowymi składnikami fazy planowania we wdrożeniu. Po utworzeniu wymiarów finansowych i kont głównych w systemie są one używane na stronach **Skonfiguruj strukturę konta**, **Struktury reguł zaawansowanych** i **Konfiguracja wymiaru finansowego dla aplikacji integrujących**. Kolejność zdefiniowana na tych stronach jest używany w systemie do wprowadzania danych i zużycia. W niektórych miejscach w systemie wymiary finansowe i konta główne są wyświetlane w oddzielnych polach. Jednak w innych miejscach, takich jak arkusze, wymiary finansowe i konta główne są wyświetlane jako jeden ciąg znaków.

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Najważniejsze wskazówki dotyczące konfigurowania wymiarów finansowych i kont głównych w systemie z pisownią od prawej do lewej

-   Po wybraniu ogranicznik dla planów kont, wybierz jedną z opcji podwójne ogranicznik: podwójny łącznik (-), pasek podwójny (|) lub podwójne kropki (.) lub podwójnego podkreślenia (\_\_).
-   Podczas tworzenia wartości wymiarów finansowych i kont głównych używaj tylko cyfr i znaków języka z pisownią od prawej do lewej.
-   Unikaj stosowania wybranego separatora planu kont w wartościach wymiarów finansowych i kont głównych.

Przestrzegając poniższych najważniejszych wskazówek, pomagasz zapewnić spójne reprezentowanie kolejności zdefiniowanej przez użytkownika w całym systemie.



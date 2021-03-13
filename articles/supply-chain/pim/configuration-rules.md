---
title: Reguły konfiguracji
description: Ten artykuł zawiera ogólne informacje o regułach konfiguracji. Reguły konfiguracji definiują relacje między towarami na liście składowej (BOM) dla produktów wykorzystujących technologię konfiguracji opartej na wymiarach.
author: cvocph
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1b8b3de89235c6dac52f059af9665ea70f80d83a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007802"
---
# <a name="configuration-rules"></a>Reguły konfiguracji

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera ogólne informacje o regułach konfiguracji. Reguły konfiguracji definiują relacje między towarami na liście składowej (BOM) dla produktów wykorzystujących technologię konfiguracji opartej na wymiarach.

Reguły konfiguracji są dostępne podczas definiowania modeli konfiguracji opartych na wymiarach. Reguły konfiguracji są używane do wymuszania albo zakazywania kombinacji określonych towarów na liście składowej (BOM). Po utworzeniu BOM i przypisaniu odpowiednich towarów do odpowiednich grup konfiguracji, można zdefiniować jedną lub więcej reguł konfiguracji. Jeżeli dwa towary przynależą do siebie, można je ze sobą połączyć za pomocą operatora **Zaznacz**. Jeśli dwa towary wzajemnie się wykluczają, można je od siebie oddzielić za pomocą operatora **Odznacz**.  

**Uwaga:** ta informacja dotyczy tylko produktów głównych, które używają technologii konfiguracji opartej na wymiarach.  

Istniejące konfiguracje nie są objęte kolejnymi zmianami reguł konfiguracji. Jednak przed zdefiniowaniem nowej konfiguracji konieczne jest określenie reguł lub ich sprawdzenie, jeśli istnieje podejrzenie o zmianie reguł.  

**Uwaga:** dla metody **Zaznacz** pochodna grupa konfiguracji, numer towaru i konfiguracja wybierane są automatycznie. Dla metody **Odznacz** pochodna grupa konfiguracji, numer towaru i konfiguracja nie może zostać wybrana.

<a name="additional-resources"></a>Dodatkowe zasoby
--------

[Omówienie konfiguracji produktów opartych na wymiarach](dimension-based-product-configuration.md)




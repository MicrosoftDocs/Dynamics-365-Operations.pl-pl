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
ms.search.scope: Core, Operations
ms.custom: 19761
ms.assetid: e4c6622d-1e2d-4a4d-8047-c553a25d4f87
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0eb925253962df6c85e935b8d8e53d93af38c16
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208577"
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




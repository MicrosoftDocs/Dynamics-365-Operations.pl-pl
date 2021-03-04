---
title: Konfigurowanie nazw arkuszy wynajmu
description: W tym temacie opisano sposób definiowania nazw arkuszy wynajmu. Nazwy arkuszy wynajmu określają arkusze, w których są księgowane wpisy inicjowane z modułu Wynajem składnika majątku.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e8b1b908dfd6d1d6072b6efa83f13ae5784c85c1
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4446989"
---
# <a name="set-up-lease-journal-names"></a>Konfigurowanie nazw arkuszy wynajmu

[!include [banner](../includes/banner.md)]

Nazwy arkuszy wynajmu określają arkusze, w których są księgowane transakcje z modułu Wynajem składnika majątku. Tylko nazwy arkuszy przypisane do typu arkusza **Wynajem składnika majątku** są wyświetlane w polach **Początkowe rozpoznawanie** i **Nazwa arkusza miesięcznego** na stronie **Parametry wynajmu składników majątku**. Do pola **Nazwa arkusza faktur** można przypisać tylko typ arkusza **Rejestracja faktury dostawcy**.

Aby skonfigurować nazwy arkuszy wynajmu, wykonaj następujące kroki.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.
2. Na karcie **Ogólne** w polu **Nazwa arkusza początkowego ujęcia** wybierz arkusz. Wszystkie wpisy w arkuszu dotyczące początkowego ujęcia będą księgowane w arkuszu o tej nazwie.
3. W polu **Nazwa arkusza faktur** wybierz arkusz. Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Tak** w księdze wynajmu, faktury opłat z tytułu wynajmu i płatności wydatków będą księgowane w arkuszu o tej nazwie.
4. W polu **Nazwa arkusza wynajmu** wybierz arkusz. Wszystkie wpisy dotyczące amortyzacji, odsetek i przeklasyfikowania zobowiązań krótkoterminowych będą księgowane w arkuszu o tej nazwie. Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Nie** w księdze wynajmu, wpisy opłat z tytułu wynajmu i płatności wydatków również będą księgowane w arkuszu o tej nazwie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
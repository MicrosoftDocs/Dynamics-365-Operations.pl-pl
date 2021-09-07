---
title: Konfigurowanie nazw arkuszy wynajmu
description: W tym temacie opisano sposób definiowania nazw arkuszy wynajmu. Nazwy arkuszy wynajmu określają arkusze, w których są księgowane wpisy inicjowane z modułu Wynajem składnika majątku.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 1ea35ec40ddd459e1a9e7641557147e23fe45d3e
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7343221"
---
# <a name="set-up-lease-journal-names"></a>Konfigurowanie nazw arkuszy wynajmu

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Nazwy arkuszy wynajmu określają arkusze, w których są księgowane transakcje z modułu Wynajem składnika majątku. Tylko nazwy arkuszy przypisane do typu arkusza **Wynajem składnika majątku** są wyświetlane w polach **Początkowe rozpoznawanie** i **Nazwa arkusza miesięcznego** na stronie **Parametry wynajmu składników majątku**. Do pola **Nazwa arkusza faktur** można przypisać tylko typ arkusza **Rejestracja faktury dostawcy**.

System blokuje możliwość edytowania niektórych pól finansowych, aby zapobiec ewentualnym rozbieżnościom między transakcjami a harmonogramami. Do blokowanych pól należą m.in. następujące: **Konto**, **Kwoty**, **Wymiary finansowe**, **Waluta** i **Typ transakcji**. Ponadto nie można dodawać ani usuwać wierszy wpisów w arkuszu w żadnych wpisach arkusza wynajmu składnika majątku, ponieważ mogłoby to spowodować rozbieżności między harmonogramami a transakcjami.


Aby skonfigurować nazwy arkuszy wynajmu, wykonaj następujące kroki.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.
2. Na karcie **Ogólne** w polu **Nazwa arkusza początkowego ujęcia** wybierz arkusz. Wszystkie wpisy w arkuszu dotyczące początkowego ujęcia będą księgowane w arkuszu o tej nazwie.
3. W polu **Nazwa arkusza faktur** wybierz arkusz. Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Tak** w księdze wynajmu, faktury opłat z tytułu wynajmu i płatności wydatków będą księgowane w arkuszu o tej nazwie.
4. W polu **Nazwa arkusza wynajmu** wybierz arkusz. Wszystkie wpisy dotyczące amortyzacji, odsetek i przeklasyfikowania zobowiązań krótkoterminowych będą księgowane w arkuszu o tej nazwie. Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Nie** w księdze wynajmu, wpisy opłat z tytułu wynajmu i płatności wydatków również będą księgowane w arkuszu o tej nazwie.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

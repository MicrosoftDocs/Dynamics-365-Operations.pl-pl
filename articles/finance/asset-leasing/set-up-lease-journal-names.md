---
title: Konfigurowanie nazw arkuszy wynajmu
description: W tym artykule opisano sposób definiowania nazw arkuszy wynajmu. Nazwy arkuszy wynajmu określają arkusze, w których są księgowane wpisy inicjowane z modułu Wynajem składnika majątku.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 678587e0846f6ce6d6d8113290a90b3f4d1988cc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874704"
---
# <a name="set-up-lease-journal-names"></a>Konfigurowanie nazw arkuszy wynajmu

[!include [banner](../includes/banner.md)]


Nazwy arkuszy wynajmu określają arkusze, w których są księgowane transakcje z modułu Wynajem składnika majątku. Tylko nazwy arkuszy przypisane do typu arkusza **Wynajem składnika majątku** są wyświetlane w polach **Początkowe rozpoznawanie** i **Nazwa arkusza miesięcznego** na stronie **Parametry wynajmu składników majątku**. Do pola **Nazwa arkusza faktur** można przypisać tylko typ arkusza **Rejestracja faktury dostawcy**.

System blokuje możliwość edytowania niektórych pól finansowych, aby zapobiec ewentualnym rozbieżnościom między transakcjami a harmonogramami. Do blokowanych pól należą m.in. następujące: **Konto**, **Kwoty**, **Wymiary finansowe**, **Waluta** i **Typ transakcji**. Ponadto nie można dodawać ani usuwać wierszy wpisów w arkuszu w żadnych wpisach arkusza wynajmu składnika majątku, ponieważ mogłoby to spowodować rozbieżności między harmonogramami a transakcjami.


Aby skonfigurować nazwy arkuszy wynajmu, wykonaj następujące kroki.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.
2. Na karcie **Ogólne** w polu **Nazwa arkusza początkowego ujęcia** wybierz arkusz. Wszystkie wpisy w arkuszu dotyczące początkowego ujęcia będą księgowane w arkuszu o tej nazwie.
3. W polu **Nazwa arkusza faktur** wybierz arkusz. Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Tak** w księdze wynajmu, faktury opłat z tytułu wynajmu i płatności wydatków będą księgowane w arkuszu o tej nazwie.
4. W polu **Nazwa arkusza wynajmu** wybierz arkusz. Wszystkie wpisy dotyczące amortyzacji, odsetek i przeklasyfikowania zobowiązań krótkoterminowych będą księgowane w arkuszu o tej nazwie. Jeśli opcja **Płatność dla dostawcy** jest ustawiona na **Nie** w księdze wynajmu, wpisy opłat z tytułu wynajmu i płatności wydatków również będą księgowane w arkuszu o tej nazwie.
5. W polu **Nazwa arkusza modyfikacji wynajmu** wybierz arkusz. W tej nazwie arkusza będą księgowane transakcje korekty dzierżawy, zakończenia i utraty wartości. Do wybranej nazwy arkusza nie powinien być przypisany przepływ pracy ani zatwierdzenie. Jeśli nazwa arkusza modyfikacji dzierżawy nie zostanie zdefiniowana, transakcje korekty dzierżawy, zakończenia i utraty wartości zostaną zaksięgowane w nazwie arkusza wybranego w polu **Nazwa arkusza wynajmu**. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

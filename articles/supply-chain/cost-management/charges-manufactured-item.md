---
title: Wyświetlanie opłat związanych z wytworzonym towarem
description: Stałe koszty wytworzonego towaru odzwierciedlają czas przezbrajania dla danej operacji oraz składniki o stałej ilości lub stałą ilość odpadków.
author: JennySong-SH
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: f97495488dbbe504a5e79ef7f65fa97eb287d17b
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675439"
---
# <a name="display-charges-for-a-manufactured-item"></a>Wyświetlanie opłat związanych z wytworzonym towarem

[!include [banner](../includes/banner.md)]

Stałe koszty wytworzonego towaru odzwierciedlają czas przezbrajania dla danej operacji oraz składniki o stałej ilości lub stałą ilość odpadków.

Obliczona kwota zamortyzowanych opłat za towar może być wyświetlana w kosztach jednostkowych towaru. Jednak opłaty są czasami wyświetlane w oddzielnych polach i nie są uwzględniane w kosztach jednostkowych towaru. Gdy opłaty są wyświetlane w oddzielnych polach, jedno z nich przedstawia całkowitą kwotę, a drugie wielkość partii do wyceny używaną na potrzeby amortyzowania kwoty. Na przykład na stronie Cena pozycji są wyświetlane opłaty w dwóch oddzielnych polach. Jednak na stronie Pełna informacja jest wyświetlany całkowity koszt jednostki towaru, a zamortyzowane koszty są uwzględniane w kosztach jednostkowych.

Opłaty za wytwarzany towar są zawsze uwzględniane w koszcie jednostkowym tego towaru na potrzeby obliczania kosztu standardowego. Opcjonalnie mogą być też uwzględniane w planowaniu kosztów. Zasada w wersji wyceny wymusza uwzględnienie opłat w koszcie wytwarzanego towaru. Po aktywowaniu rekordu kosztów towaru aktualizujesz opłaty w informacjach o koszcie podstawowym towaru, które są wyświetlane na stronie Cena pozycji. Opłaty są wyświetlane w dwóch oddzielnych polach i nie są uwzględniane w koszcie jednostkowym towaru. Po każdym aktywowaniu nastąpi aktualizacja informacji o koszcie podstawowym towaru, nawet jeśli aktywacja odzwierciedla dane z różnych oddziałów. W związku z tym informacje o kosztach podstawowych powinny być traktowane jako dane referencyjne.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
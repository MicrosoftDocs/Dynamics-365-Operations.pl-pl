---
title: Konfigurowanie stawek indeksowanych
description: W tym artykule opisano sposób konfigurowania stawek indeksowanych. Stawki indeksowane są wymagane, jeśli w organizacji kwoty opłat z tytułu wynajmu są łączone ze zbiorem stawek indeksowanych.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e700c6c0c66b855a3e329302ac27681f4d0144a7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883395"
---
# <a name="set-up-index-rates"></a>Konfigurowanie stawek indeksowanych

[!include [banner](../includes/banner.md)]

Jeśli opłaty z tytułu wynajmu są uzależnione od indeksu, typy stawek indeksowanych można dodawać i obsługiwać w systemie. Aby przeszacować opłaty z tytułu wynajmu na stronie **Typ stawki indeksowanej**, proces przeszacowania stawki indeksowanej używa najnowszej stawki indeksowanej z dnia przeszacowania.

Aby dodać typy stawek indeksowanych i stawki indeksowane, wykonaj następujące kroki.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Typ stawki indeksowanej**.
2. Wybierz pozycję **Nowy**.
3. W odpowiednich polach wprowadź typ stawki oraz nazwę stawki indeksowanej.
4. Aby dodać nową wartość stawki indeksowanej, wybierz typ stawki indeksowanej, a następnie wybierz opcję **Dodaj**.
5. Zaznacz datę wejścia stawki w życie, a następnie wybierz wartość stawki.

Jako metodę stawki indeksowanej należy wybrać opcję **Różnica wartości stawki indeksowanej** lub **Wartość stawki indeksowanej**.

- Wybierz metodę **Różnica wartości stawki indeksowanej**, aby obliczać nową opłatę z tytułu wynajmu na podstawie różnicy między stawką indeksowaną w dniu rozpoczęcia a najbardziej aktualną stawką indeksowaną. Stawkę indeksowaną ustawia się w polu **Stawka indeksowana (%)**.
- Wybierz metodę **Wartość stawki indeksowanej**, aby obliczać opłatę z tytułu wynajmu przy użyciu wartości procentowej określonej w polu **Stawka indeksowana (%)**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

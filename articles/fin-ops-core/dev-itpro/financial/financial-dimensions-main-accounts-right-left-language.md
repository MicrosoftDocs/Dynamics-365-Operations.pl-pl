---
title: Wymiary finansowe i konta główne w językach pisanych od prawej do lewej
description: W tym artykule opisano decyzje, które należy podjąć w przypadku używania języka z pisownią od prawej do lewej, gdy trzeba skonfigurować wymiary finansowe i konta główne.
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b1e2c0ef5cd405232332847078c70af42f056e17
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8866768"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>Wymiary finansowe i konta główne w językach pisanych od prawej do lewej

[!include [banner](../includes/banner.md)]

W tym artykule opisano niektóre decyzje wdrożeniowe, które należy podjąć w przypadku używania języka z pisownią od prawej do lewej, gdy trzeba skonfigurować wymiary finansowe i konta główne.

Wymiary finansowe i konta główne są kluczowymi składnikami fazy planowania we wdrożeniu. Po utworzeniu wymiarów finansowych i kont głównych w systemie są one używane na stronach **Skonfiguruj strukturę konta**, **Struktury reguł zaawansowanych** i **Konfiguracja wymiaru finansowego dla aplikacji integrujących**. Kolejność zdefiniowana na tych stronach jest używany w systemie do wprowadzania danych i zużycia. W niektórych miejscach w systemie wymiary finansowe i konta główne są wyświetlane w oddzielnych polach. W innych miejscach, takich jak arkusze, wymiary finansowe i konta główne są wyświetlane jako jeden ciąg znaków.

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Najważniejsze wskazówki dotyczące konfigurowania wymiarów finansowych i kont głównych w systemie z pisownią od prawej do lewej

- Wybierając separator dla planów kont, wybierz jeden z separatorów podwójnych: podwójny łącznik (`--`), podwójną kreskę pionową (`||`), podwójną kropkę (`..`) lub podwójne podkreślenie (`\\`).
- Podczas tworzenia wartości wymiarów finansowych i kont głównych używaj tylko cyfr i znaków języka z pisownią od prawej do lewej.
- Unikaj stosowania wybranego separatora planu kont w wartościach wymiarów finansowych i kont głównych.

Przestrzegając poniższych najważniejszych wskazówek, pomagasz zapewnić spójne reprezentowanie kolejności zdefiniowanej przez użytkownika w całym systemie.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

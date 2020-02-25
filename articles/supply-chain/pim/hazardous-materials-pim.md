---
title: Materiały niebezpieczne
description: Ten temat zawiera informacje dotyczące dokumentów i informacje dotyczące materiałów niebezpiecznych przechowywanych w środowisku użytkownika.
author: lachlancashMS
manager: AnnBe
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2019-10-14
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76dd6539e39bb77c546e613b290fc5decba9457f
ms.sourcegitcommit: 4c60f5dccdf0b94ed110a657ef331546adc5424a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/23/2020
ms.locfileid: "2982315"
---
# <a name="hazardous-materials"></a>Materiały niebezpieczne

[!include [banner](../includes/banner.md)]

Informacje dotyczące materiałów niebezpiecznych są konfigurowane w module Zarządzanie informacjami o produktach. Moduł ten zapewnia również dokumenty, które można wydrukować za pomocą modułu Zarządzanie magazynem.

W przypadku wysyłki materiałów sklasyfikowanych jako towary niebezpieczne, do wysyłek należy dołączyć dodatkową dokumentację. Funkcje materiałów niebezpiecznych umożliwiają klientom przechowywanie informacji dotyczących klasyfikacji i powiązanie ich ze zwalnianiem towarów. Te informacje mogą być następnie używane w celu przygotowania dokumentacji dotyczącej wysyłki.

> [!IMPORTANT]
> Aby ułatwić zarządzanie wysyłką towarów niebezpiecznych, program Microsoft Dynamics 365 Supply Chain Management umożliwia skonfigurowanie dodatkowych informacji dotyczących produktów, które są związane z produktami. Można również skonfigurować dodatkowe dokumenty wysyłki. Jednak system nie jest automatycznie zgodny z przepisami dotyczącymi danego kraju lub regionu. Zamiast tego jest to narzędzie, które może pomóc w ogólnym programie.

Aby można było skorzystać z tej funkcji, wymagane są następujące ustawienia:

- **Zarządzanie informacjami o produktach:** umożliwia konfigurowanie kodów, które można stosować w odniesieniu do zwolnionych produktów.
- **Zarządzanie magazynem** umożliwia drukowanie informacji o wysyłce przy użyciu dodatkowych dokumentów dotyczących wysyłki.

## <a name="product-information-management"></a>Zarządzanie informacjami o produktach

W module Zarządzanie informacjami o produktach istnieje zakres tabel ustawień, w którym można dodać informacje o odwołaniach, które znajdują się w wykazach towarów niebezpiecznych dla transportu drogowego, powietrznego i morskiego.

Oto kilka dostępnych regulacji, które często są używane:

- **ADR** — przepisy dotyczące międzynarodowego przewozu drogowego towarów niebezpiecznych
- **CFR 49** — przepisy w USA dot. przewozu towarów niebezpiecznych
- **IMDG** — Międzynarodowy kodeks ładunków niebezpiecznych (IMDG)
- **IATA** — regulacje dotyczące towarów niebezpiecznych międzynarodowego zrzeszenia przewoźników powietrznych (IATA)

Każde z tych rozporządzeń zawiera listę towarów niebezpiecznych, która zawiera kody referencyjne. Listy dla każdego typu transportu są łączone na wspólnych międzynarodowych klasyfikacjach. Program Supply Chain Management zawiera tabelę odwołań dla współdzielonych kodów z tych list. Każda lista ma również kilka unikatowych kodów, które można zdefiniować.

Aby rozpocząć konfigurowanie tych informacji, należy utworzyć rozporządzenie, które będzie używane do konfigurowania początkowych parametrów.

## <a name="warehouse-management"></a>Zarządzanie magazynem

Po przygotowaniu wysyłki można wydrukować kilka nowych raportów. W tych raportach są używane informacje skonfigurowane w module Zarządzanie informacjami o produktach.

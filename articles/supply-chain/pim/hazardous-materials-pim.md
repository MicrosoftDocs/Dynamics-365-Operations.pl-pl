---
title: Materiały niebezpieczne
description: Ten temat zawiera informacje dotyczące dokumentów i informacje dotyczące materiałów niebezpiecznych przechowywanych w środowisku użytkownika.
author: lachlancashMS
manager: tfehr
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
ms.openlocfilehash: 079c8d23250368c92e5d79f0e2624f8340db2077
ms.sourcegitcommit: c009ec75f53872272f11c92a1ce81a391e3845a2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "3699543"
---
# <a name="hazardous-materials"></a>Materiały niebezpieczne

[!include [banner](../includes/banner.md)]

Informacje dotyczące materiałów niebezpiecznych są konfigurowane w module Zarządzanie informacjami o produktach. Moduł ten zapewnia również dokumenty, które można wydrukować za pomocą modułu Zarządzanie magazynem.

W przypadku wysyłki materiałów sklasyfikowanych jako towary niebezpieczne, do wysyłek należy dołączyć dodatkową dokumentację. Funkcje materiałów niebezpiecznych umożliwiają klientom przechowywanie informacji dotyczących klasyfikacji i powiązanie ich ze zwalnianiem towarów. Te informacje mogą być następnie używane w celu przygotowania dokumentacji dotyczącej wysyłki.

> [!IMPORTANT]
> Funkcje dot. materiałów niebezpiecznych w Microsoft Dynamics 365 Supply Chain Management zawierają użyteczny zbiór pól informacji o produktach i związanych z nimi funkcji, które mogą pomóc w rejestrowaniu i odnajdywaniu informacji związanych z produktami niebezpiecznymi. Te funkcje mogą również pomóc w projektowaniu i drukowaniu dokumentów dostawy, które zawierają niektóre z tych samych informacji o wszelkich transportowanych niebezpiecznych materiałach. Jednak system nie sprawi, że działania będą automatycznie zgodne ze wszystkimi przepisami danego kraju lub regionu. Chociaż narzędzia te mają na celu ułatwienie zgodności ze wspólnymi przepisami, same w sobie nie są wystarczające ani nie gwarantują poprawności. Twoja organizacja jest odpowiedzialna za zastosowanie wszystkich stosownych rozporządzeń i podjęcie wszelkich niezbędnych kroków w celu przestrzegania odpowiednich przepisów.

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

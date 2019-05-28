---
title: Planowanie planu kont
description: Ten temat zawiera informacje, które pomogą zaprojektować plan kont w organizacji.
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 93d5ef19a4b1cb2885c611c8675ac06fd841ac56
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556646"
---
# <a name="plan-your-chart-of-accounts"></a>Planowanie planu kont

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje, które pomogą zaprojektować plan kont w organizacji.

Do śledzenia i obsługi informacji finansowych w organizacji można skonfigurować plan kont. Plan kont jest to zbiór kont, które definiują ramy finansowe. Aby jeszcze dokładniej śledzić transakcje na tych kontach, można dodawać segmenty nazywane wymiarami finansowymi. Na przykład, konto wydatków może zawierać wymiary finansowe o nazwie Dział, MPK oraz Cel. Zdefiniowane przez użytkownika reguły decydują o tym, jak te wymiary finansowe są dołączane do kont głównych i innych wymiarów finansowych, i jak wprowadzane są transakcje. Te zdefiniowane przez użytkownika reguły są nazywane strukturami kont i regułami zaawansowanymi.

Plan kont jest to usystematyzowana lista kont księgi głównej firmy. Lista służy do przygotowywania raportów finansowych dla urzędów i właścicieli. Konta są najpierw grupowane w typy, a następnie łączone w większe kategorie. Na poziomie najbardziej ogólnym, konta są pogrupowane jako przychody i koszty (konta operacyjne) oraz jako aktywa i pasywa (konta bilansowe).

Plan kont może być udostępniany i używany przez dowolną firmę w organizacji. Plan kont używany przez firmę definiuje się na stronie **Księga**.

Oto kilka czynników, które należy uwzględnić podczas planowania struktury planu kont w organizacji:

- Wymagania dotyczące raportowania w kraju lub regionie, w którym mieści się organizacja
- Wymagania dotyczące raportowania firmy
- Poziom wymaganej specyfikacji zarówno dla zewnętrznych organizacji, jak i dla Twojej organizacji

Plan kont tworzy się na stronie **Plan kont**. Konta główne można tworzyć na stronie **Plan kont** lub na stronie **Konta główne**. Na kontach głównych nie należy używać żadnych znaków specjalnych, które są używane jako separatory planów kont. W przeciwnym razie może wystąpić niestabilność lub zawsze trzeba będzie używać wyszukiwań albo okna dialogowego podczas wprowadzania kombinacji kont i wymiarów. Aby uzyskać więcej informacji, zobacz [Tworzenie konta głównego](tasks/create-main-account.md).

> [!NOTE]
> W programie Microsoft Dynamics for Finance and Operations w wersji 8.0 (z kwietnia 2018 r.) można zmodyfikować separator planu kont ze strony **Parametry księgi głównej**.

Dobrze jest połączyć konta główne z kategoriami konta głównego, by móc korzystać z domyślnych raportów finansowych bez konieczności wprowadzania żadnych zmian. Dzięki temu tworzenie i obsługa raportów staje się łatwiejsza.

Struktury kont tworzy się na stronie **Skonfiguruj strukturę konta**. Struktury kont definiują prawidłowe kombinacje. Te kombinacje, łącznie z kontami głównymi, tworzą plan kont. Aby uzyskać więcej informacji, zobacz [Tworzenie struktur kont](tasks/create-account-structures.md).

**Firma zastępuje**

Nie wszystkie konta główne są prawidłowe dla wszystkich firm, a niektóre konta główne mogą działać tylko w określonym przedziale czasu. W tym scenariuszu można w sekcji **Firma zastępuje** wskazać firmy, dla których konto główne powinno być zawieszone, właściciela oraz okres aktywności wymiaru. Zastąpienia na poziomie wspólnym nie mogą być bardziej restrykcyjne niż zastąpienia na poziomie firmy.

Aby uzyskać więcej informacji, zobacz następujące tematy:

- [Wymiary finansowe](financial-dimensions.md)
- [Tworzenie i przypisywanie struktur reguł zaawansowanych](tasks/create-assign-advanced-rule-structures.md)

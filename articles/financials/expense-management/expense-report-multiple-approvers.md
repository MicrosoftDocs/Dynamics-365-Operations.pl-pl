---
title: "Raporty z wydatków i wiele osób zatwierdzających"
description: "Ten temat zawiera informacje dotyczące raportów z wydatków, które wymagają zatwierdzenia przez więcej niż jedną osobę."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 0f7592c580a21040c8b630885939ceaab3855c2c
ms.contentlocale: pl-pl
ms.lasthandoff: 03/13/2018

---

# <a name="expense-reports-and-multiple-approvers"></a>Raporty z wydatków i wiele osób zatwierdzających

[!include [banner](../includes/banner.md)]

W zależności od zasad zatwierdzania wydatków w organizacji kilka osób może być zobowiązanych do zatwierdzania raportu z wydatków przesłanego przez pracownika. Podczas konfigurowania procesu przepływu pracy dla zatwierdzania raportów z wydatków można dodać elementy przepływu pracy, które zawierają zadania lub kroki dla jednej lub więcej osób mających zatwierdzać raporty z wydatków. Na przykład może istnieć wymóg, aby wszystkie raporty z wydatków były najpierw zatwierdzane przez przełożonego pracownika, który złożył raport, a następnie przez koordynatora rozrachunków z dostawcami.

Jeśli zdecydujesz wprowadzić konieczność istnienia wielu osób zatwierdzających raporty z wydatków, można dodać elementy przepływu pracy na jeden z następujących sposobów:

- Dodanie jednego elementu zatwierdzania, który ma jeden krok. Na przykład krok może wymagać, aby raport z wydatków został przypisany do grupy użytkowników oraz został zaaprobowany przez 50 członków grupy użytkowników.
- Dodanie jednego elementu zatwierdzania, który ma wiele kroków. Na przykład element zatwierdzania może zawierać następujące czynności:

    1. Przełożony pracownika, który złożył raport z wydatków, zatwierdza raport.
    2. Pracownik ds. rozrachunków z dostawcami weryfikuje paragony i pozycje raportu z wydatków.
    3. Właściciel budżetu zatwierdza raport z wydatków.

- Dodanie wielu elementów zatwierdzenia, z których każdy ma jeden krok. Na przykład można dodać oddzielny element zatwierdzania dla każdego z następujących kroków:

    1. Przełożony pracownika zatwierdza raport z wydatków.
    2. Właściciel budżetu zatwierdza raport z wydatków.


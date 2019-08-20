---
title: Naruszenia zasad inspekcji i sprawy
description: W tym artykule wyjaśniono, jak są generowane sprawy inspekcji na podstawie naruszeń reguł inspekcji. Znajdują się tu także informacje o różnych sposobach, w jakie zasady inspekcji wykorzystują funkcje zakresu dat wyboru dokumentów.
author: ryansandness
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d14894d331037033b27fac3fd7ff98c5521eaf98
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1839624"
---
# <a name="audit-policy-violations-and-cases"></a>Naruszenia zasad inspekcji i sprawy

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak są generowane sprawy inspekcji na podstawie naruszeń reguł inspekcji. Znajdują się tu także informacje o różnych sposobach, w jakie zasady inspekcji wykorzystują funkcje zakresu dat wyboru dokumentów.

<a name="how-audit-cases-are-generated"></a>Jak są generowane sprawy inspekcji
-----------------------------

Zasady inspekcji są używane do identyfikowania raportów z wydatków, zamówień zakupu i faktur od dostawcy, które nie są zgodne z regułami firmy zdefiniowanymi i skonfigurowanymi jako reguły inspekcji. 

Zasady inspekcji są uruchamiane w trybie wsadowym. Po uruchomieniu zasad inspekcji wszystkie reguły należące do tej zasady są uruchamiane w tym samym czasie.

Każda reguła ocenia zestaw dokumentów. Reguła wybiera dokumenty z wybranego zakresu dat spełniające określone kryteria. Na przykład jedna reguła może wybrać raporty z wydatków, w których uwzględniono posiłki o wartości przekraczającej 50.00. Inna reguła może wybrać faktury od dostawcy, które są płatne na rzecz określonego dostawcy. Dla każdego dokumentu wskazanego w zestawie jest generowane naruszenie. Naruszenie to jest zapisem, że określony dokument, np. faktura nr 12345, jest niezgodny z regułą. 

System grupuje razem wiele rekordów naruszenia zasad inspekcji i kojarzy ze sprawami inspekcji. Domyślnie sprawy dla każdej zasady inspekcji są pogrupowane według reguły inspekcji. Można jednak wybrać inne kryteria grupowania na stronie **Kryteria grupowania przypadków**. Na przykład można pogrupować nagłówki wydatków według identyfikatora projektu i faktury od dostawcy według konta dostawcy. W takim przypadku wszystkie naruszenia nagłówka wydatków, które mają ten sam identyfikator projektu, zostaną pogrupowane w tej samej sprawie, oraz wszystkie faktury od dostawcy, które mają to samo konto dostawcy, zostaną pogrupowane w tej samej sprawie. 

> [!NOTE]
> W przypadku reguł inspekcji opartych na typie zapytania **Duplikat** naruszenia nie są pogrupowane według reguły ani według kryteriów określonych na stronie **Kryteria grupowania przypadków**. Zamiast tego są one pogrupowane według kryteriów, które są wbudowane w regułę inspekcji. Na przykład, jeśli reguła ocenia raporty z wydatków pod kątem zduplikowanych wydatków z tą samą kwotą, numerem handlowca i datą, wszystkie wydatki posiadające te same wartości w tych polach zostaną umieszczone w jednej sprawie. Wszelkie wydatki, które mają różne wartości będą osobnymi sprawami.

Po wygenerowaniu sprawy inspekcji są obsługiwane przy użyciu typowych procesów zarządzania sprawami.

## <a name="document-selection-date-ranges"></a>Wybór zakresu dat dokumentu
Po uruchomieniu zasad inspekcji, każda reguła wybiera dokumenty określonego typu z datą należącą do wskazanego zakresu. Zakres wyboru dat dokumentów określa się na stronie **Dodatkowe opcje**. Wiele dokumentów ma więcej niż jedną skojarzoną datę. Pole daty, które jest używane przez regułę inspekcji określa się na stronie **Typ reguły**.

Oto inne sposoby wykorzystania wyboru zakresu dat dokumentu przez regułę inspekcji:

-   Zasada używa wersji każdej reguły inspekcji ważnej w ostatnim dniu wyboru zakresu dat dokumentu. Ważność wszystkich reguł można sprawdzić na stronie **Zasady inspekcji**.
-   Zasady używają węzłów organizacyjnych skojarzonych z zasadą w ostatnim dniu wyboru zakresu dat dokumentu. Na stronie listy **Zasady inspekcji** widoczne są tylko węzły organizacji, które są już powiązane z zasadami.
-   W przypadku reguł opartych na typie zapytania **Wyszukiwanie wg listy** zasada ocenia dokumenty pod kątem monitorowanych jednostek, które są aktywne w ostatnim dniu wyboru zakresu dat dokumentu.


Aby uzyskać więcej informacji, zobacz [Reguły inspekcji](audit-policy-rules.md).




---
title: "Używanie funkcji szybkiego importowania/eksportowania"
description: "Celem funkcji szybkiego importowania/eksportowania jest umożliwienie użytkownikom importowania i eksportowania przy użyciu mniejszej liczby kroków."
author: margoc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: 
ms.technology: 
audience: Application User
ms.reviewer: margoc
ms.search.scope: AX 2012 R3 CU8, UnifiedOperations
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5c54d0590856755e208ada9d97af7790a6de95ec
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Uruchamianie testowego narzędzia do przenoszenia danych (wersja beta) dla systemu Dynamics AX (AX 2012)

[!include[banner](../../includes/banner.md)]


Celem funkcji szybkiego importowania/eksportowania jest umożliwienie użytkownikom importowania i eksportowania przy użyciu mniejszej liczby kroków.

Dodaliśmy funkcję Szybkie importowanie/eksportowanie, aby umożliwić użytkownikom importowanie lub eksportowanie prostych zadań, które chcą szybko wykonać. W idealnej sytuacji ta funkcja jest używana w scenariuszach, w których plik jest automatycznie mapowany do systemu, a użytkownik nie musi przechodzić przez zaawansowane mapowanie ani tworzyć powtarzających się zadań importu lub eksportu.

-   Ta funkcja obsługuje pracę z jednostkami gotowymi (standardowymi) i niestandardowymi.
-   Można importować z plików, a jeśli jest używane źródło danych ODBC, można wybrać zapytanie, które ma zostać użyte do zdefiniowania importu.
-   Muszą być wcześniej zdefiniowane formaty danych źródłowych dla systemu AX lub pliku i trzeba wiedzieć, gdzie się one znajdują.
-   Aby używać funkcji szybkiego importowania/eksportowania, nie trzeba tworzyć grupy przetwarzania. Zostanie ona utworzona automatycznie przez system podczas wykonywania zadania importu lub eksportu. Można także określić opcję przechowywania historii danych importowanych przez funkcję szybkiego importowania/eksportowania.

  Należy zauważyć, że funkcja szybkiego importowania/eksportowania zakłada, że użytkownik jest obeznany z koncepcją struktury DIXF.




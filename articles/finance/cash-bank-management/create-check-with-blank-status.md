---
title: Tworzenie czeków z pustym statusem
description: W tym temacie wyjaśniono, jak tworzyć puste czeki dla konta bankowego na stronie Czeki.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: af79dd4831f2e7fc71c296922d73a9e42f7955b3
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176053"
---
# <a name="create-checks-that-have-blank-status"></a>Tworzenie czeków z pustym statusem

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak tworzyć puste czeki. Na przykład możesz utworzyć pusty czek, aby zarejestrować czek, który został uszkodzony i nie można go wykorzystać do płatności.

Na stronie **Czeki** wykonuje się zadania konserwacyjne związane z czekami. Na przykład możesz tworzyć nowe numery czeków i usuwać czeki. Możesz także tworzyć czeki o statusie **Pusty**. Po utworzeniu pustych czeków nie można ich usunąć ani użyć ponownie w systemie.

> [!NOTE]
> Ta funkcja jest dostępna na stronie**Czeki** tylko jeśli włączysz funkcję **Twórz czeki z pustym statusem na stronie Czeki** na stronie **Zarządzanie funkcjami**. Jeśli ta funkcja nie jest włączona, czeki o statusie **Pusty** można utworzyć tylko w oknie dialogowym **Płatność czekiem** podczas procesu generowania płatności w opcji Rozrachunki z dostawcami.

Aby otworzyć stronę **Czeki**, przejdź do **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**, a następnie w okienku akcji na karcie **Zarządzanie płatnościami** w grupie**Informacje pokrewne**, wybierz opcję **Czeki**. Możesz też wybrać opcje **Zarządzanie gotówką i bankami \> Zapytania i raporty \> Czeki**.

Następnie, aby utworzyć czeki, które mają status **Pusty** w okienku akcji wybierz **Utwórz puste czeki**. Gdy system tworzy puste czeki, powiązane konto bankowe zostaje tymczasowo dezaktywowane. To zachowanie zmniejsza ryzyko, że płatności będą generowane w tym samym czasie, gdy tworzone są puste czeki. Po zakończeniu przetwarzania powiązane konto bankowe zostanie ponownie aktywowane.

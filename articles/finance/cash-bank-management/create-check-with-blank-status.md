---
title: Tworzenie czeków z pustym stanem
description: W tym artykule wyjaśniono, jak tworzyć puste czeki dla konta bankowego.
author: angelad116
ms.date: 10/24/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 86020d9088d8135c83716128a77090608536a78f
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804027"
---
# <a name="create-checks-that-have-blank-status"></a>Tworzenie czeków z pustym stanem

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak tworzyć puste czeki. Na przykład możesz utworzyć pusty czek, aby zarejestrować czek, który został uszkodzony i nie można go wykorzystać do płatności.

Na stronie **Czeki** wykonuje się zadania konserwacyjne związane z czekami. Na przykład możesz tworzyć nowe numery czeków i usuwać czeki. Możesz także tworzyć czeki o statusie **Pusty**. Po utworzeniu pustych czeków nie można ich usunąć ani użyć ponownie w systemie.

> [!NOTE]
> Ta funkcja jest dostępna na stronie **Czeki** tylko jeśli włączysz funkcję **Twórz czeki z pustym statusem na stronie Czeki** na stronie **Zarządzanie funkcjami**. Jeśli ta funkcja nie jest włączona, czeki o statusie **Pusty** można utworzyć tylko w oknie dialogowym **Płatność czekiem** podczas procesu generowania płatności w opcji Rozrachunki z dostawcami.

Aby otworzyć stronę **Czeki**, przejdź do **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**, a następnie w okienku akcji na karcie **Zarządzanie płatnościami** w grupie **Informacje pokrewne**, wybierz opcję **Czeki**. Możesz też wybrać opcje **Zarządzanie gotówką i bankami \> Zapytania i raporty \> Czeki**.

Następnie, aby utworzyć czeki, które mają stan **Pusty** w okienku akcji wybierz **Utwórz puste czeki**. Podczas tworzenia pustych czeków powiązane konto bankowe zostaje tymczasowo dezaktywowane. To zachowanie zmniejsza ryzyko, że płatności będą generowane w tym samym czasie, gdy tworzone są puste czeki. Po zakończeniu przetwarzania powiązane konto bankowe zostanie ponownie aktywowane.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

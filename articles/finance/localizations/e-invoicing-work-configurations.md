---
title: Praca z konfiguracjami
description: Ten artykuł zawiera omówienie głównego scenariusza pracy z konfiguracjami raportowania elektronicznego (ER) w obszarze roboczym Funkcje globalizacji.
author: gionoder
ms.date: 01/26/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: d87559405d2490c314eb2c8b88268af0dc0dfaca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283064"
---
# <a name="work-with-configurations"></a>Praca z konfiguracjami

[!include [banner](../includes/banner.md)]

Konfiguracje raportowania elektronicznego (ER) są jednym z głównych zestawów składników funkcji fakturowania elektronicznego. Konfiguracja ER zawiera konfigurację struktury plików i zestaw reguł transformacji do przekształcania danych na dwa sposoby:

- **Eksportuj konfigurację formatu ER** — ta konfiguracja przekształca dane ze ujednoliconej struktury wewnętrznej (modelu ER) do formatu pliku elektronicznego.
- **Importuj konfigurację formatu ER** — Ta konfiguracja przekształca dane z formatu pliku elektronicznego do ujednoliconej struktury wewnętrznej (model ER).

Oprócz generowania wychodzących plików elektronicznych we wstępnie zdefiniowanym formacie konfiguracje ER są powszechnie używane do analizowania wiadomości przychodzących z zewnętrznych usług sieci Web jako odpowiedzi. Ta funkcjonalność pomaga zbudować konfigurowalną logikę, aby uzyskać wyniki komunikacji z kanałami zewnętrznymi, przekonwertować te wyniki (kody, wiadomości i logi) do struktury czytelnej dla użytkownika, a następnie przekazać te informacje do aplikacji klienckiej.

Aby rozpocząć korzystanie z konfiguracji ER w funkcji fakturowania elektronicznego, należy połączyć je z funkcją i udostępnić je na karcie **Konfiguracje** dla bieżącej wersji funkcji. Użytkownik może pracować z połączonymi konfiguracjami ER, wybierając opcję **Dodaj**, **Usuń**, **Edytuj** lub **Wyświetl**.

Aby było można dodać łącze do konfiguracji ER, konfiguracja musi istnieć w repozytorium usługi Regulatory Configuration Service (RCS). Aby przejrzeć konfiguracje rej. dostępne w repozytorium RCS, należy wykonać następujące kroki.

1. Zaloguj się do swojego konta RCS.
2. W obszarze roboczym **Raportowanie elektroniczne** w sekcji **Konfiguracje** wybierz kafelek **Konfigracje raportowanias**.

Aby uzyskać informacje dotyczące sposobu tworzenia nowej konfiguracji raportowania elektronicznego lub importowania istniejącej konfiguracji raportowania elektronicznego z repozytorium globalnym, zobacz [raportowanie elektroniczne](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

Aby skorygować konfigurację połączonego dostawcy elektronicznego, wybierz pozycję **Edycja** na karcie **Konfiguracje** dla bieżącej funkcji fakturowania elektronicznego. System automatycznie tworzy wersję konfiguracji ER. Jeśli bieżąca wersja nie została utworzona przez aktywnego dostawcę konfiguracji, system tworzy wersję pochodną, która używa dostawcy konfiguracji. Jeśli bieżąca wersja została utworzona przez aktywnego dostawcę konfiguracji, system utworzy nową wersję. W obu przypadkach możesz zmodyfikować utworzoną wersję, a następnie automatycznie wykonać wszystkie wymagane aktualizacje.

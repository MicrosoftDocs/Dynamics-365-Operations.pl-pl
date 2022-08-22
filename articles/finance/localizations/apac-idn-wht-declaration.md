---
title: Raport potrąconych zaliczek na podatek dla Indonezji
description: W tym artykule wyjaśniono, jak skonfigurować i wygenerować raport potrąconych zaliczek na podatek dla Indonezji.
author: AdamTrukawka
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-12-02
ms.dyn365.ops.version: 10.0.20
ms.search.scope: ''
ms.openlocfilehash: 732db563532ebc46c7b9fc69c2aaa128640084f5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282444"
---
# <a name="withholding-tax-report-for-indonesia-id-00005"></a>Raport potrąconych zaliczek na podatek dla Indonezji (ID-00005)

[!include [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak skonfigurować i wygenerować plik potrąconych zaliczek na podatek (PPH), którego osoby prawne w Indonezji używają w celu raportowania transakcji potrącenia zaliczek w aplikacji e-Bupot.

Urząd skarbowy Indonezji (DGT) ustala, że podlegający opodatkowaniu przedsiębiorcy (PKP), którzy są zarejestrowani w KPP Pratama jako osoby potrącające zaliczki lub pobierające podatek dochodowy (PPH) na podstawie Artykułu 23 i/lub Artykułu 26, muszą raportować elektronicznie zwrot podatku dochodowego na podstawie Artykułów 23 i 26 za pomocą aplikacji e-Bupot. 

- **Artykuł 23** — raport zawiera wszystkie transakcje potrącenia zaliczek od dostawców, dla których kodem kraju/regionu w adresie podstawowym jest kod Indonezji.
- **Artykuł 26** — raport zawiera wszystkie transakcje potrącenia zaliczek od dostawców, dla których kodem kraju/regionu w adresie podstawowym nie jest kod Indonezji.

## <a name="prerequisites"></a>Wymagania wstępne

- Podstawowy adres osoby prawnej musi znajdować się w Indonezji.
- W obszarze **Zarządzanie funkcjami** musi być włączona funkcja **Globalna potrącona zaliczka na podatek**. Aby uzyskać więcej informacji o włączaniu funkcji, zobacz [Zarządzanie funkcjami — omówienie.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

### <a name="download-electronic-reporting-configurations"></a>Pobieranie konfiguracji raportowania elektronicznego

Plik importu jest generowany na podstawie konfiguracji raportowania elektronicznego (ER). Aby uzyskać więcej informacji o możliwościach i pojęciach dotyczących raportowania konfigurowalnego, zobacz temat [Raportowanie elektroniczne](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

W przypadku środowisk produkcyjnych i środowisk testowania akceptacyjnego przez użytkowników (UAT) postępuj zgodnie z instrukcjami w artykule [Pobieranie konfiguracji raportowania elektronicznego z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Aby wygenerować plik importu, przekaż następujące konfiguracje z repozytorium:

- **Tax declaration model.version.93.xml** lub nowsza wersja
- **Tax declaration model mapping.version.93.153.xml** lub nowsza wersja
- **WHT PPh schema import (ID).version.93.14** lub nowsza wersja

## <a name="set-up-general-ledger-parameters"></a>Konfigurowanie parametrów księgi głównej

1. Wybierz kolejno opcje **Podatek** \> **Ustawienia** \> **Parametry księgi głównej**.
2. Na karcie **Potrącona zaliczka na podatek** w polu **Mapowanie formatu deklaracji WHT** wybierz pozycję **Import schematu WHT PPh (ID)**. 
3. Wybierz kolejno pozycje **Podatek** \> **Ustawienia** \> **Potrącona zaliczka na podatek** \> **Typy przychodu potrąconej zaliczki na podatek**, aby skonfigurować typ przychodu potrąconej zaliczki na podatek **Kode Bukti Potong**, a następnie przypisać kody do powiązanych grup potrąconych zaliczek na podatek od pozycji. Te kody są wymagane do wygenerowania pliku integracji przy użyciu aplikacji e-Bupot. 

## <a name="generate-the-withholding-import-file"></a>Generowanie pliku importu potrąconych zaliczek na podatek

Proces przygotowywania i generowania pliku aplikacji e-Bupot dla określonego okresu jest oparty na transakcjach potrącenia zaliczki na podatek, które zostały zaksięgowane podczas wykonywania zadania rozliczania lub księgowania podatku od płatności.

Wykonaj poniższe kroki, aby wygenerować plik.

1. Wybierz kolejno pozycje **Podatek** \> **Deklaracje** \> **Potrącona zaliczka na podatek** \> **Plik importu PPH aplikacji e-bupot 23 i 26**.
2. Wybierz datę rozpoczęcia i zakończenia do użycia w raporcie, a następnie wybierz okres rozliczeniowy.
3. Wprowadź datę transakcji, a następnie wybierz pozycję **OK**.
4. Wybierz język. Wszystkie raporty są tłumaczone na język angielski (USA) (**en-us**) oraz indonezyjski (**id**).
5. Wybierz typ firmy, a następnie wprowadź numery czeków i dokumentów. 
6. Sprawdź, czy raport został podpisany przez menedżera. Te informacje są raportowane w pliku. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

---
title: Komponenty funkcji globalizacji
description: Ten artykuł zawiera omówienie składników funkcji globalizacji.
author: gionoder
ms.date: 02/11/2022
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
ms.openlocfilehash: 94e2d118c332a15f41f33184f5e44b0fdaccd000
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275235"
---
# <a name="globalization-feature-components"></a>Komponenty funkcji globalizacji

[!include [banner](../includes/banner.md)]

Funkcja globalizacji to zestaw składników, które definiują reguły transformacji danych w konfiguracjach raportowania elektronicznego (ER). Komponenty te obejmują instrukcje przetwarzania dokumentów elektronicznych, a następnie wysyłania ich lub odbierania z kanałów zewnętrznych. Obejmują one również warunki określające, kiedy funkcja powinna być uruchamiana dla przychodzących danych biznesowych.

Wszystkie składniki zależą od siebie. Funkcje globalizacji ułatwiają tworzenie i utrzymywanie tej zależności oraz obsługę zarządzania cyklem życia i wersjonowania zestawu składników.

## <a name="access-electronic-invoicing-feature-components"></a>Dostęp do komponentów funkcji fakturowania elektronicznego 

1. Zaloguj się na konto usługi Regulatory Configuration Services (RCS).
2. Otwórz nowy obszar roboczy **Funkcja globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Faktury elektroniczne**.

    Funkcje globalizacji mają kilka składników. Strona **Funkcje fakturowania elektronicznego** zawiera osobne karty dla każdego składnika.

    - **Wersja** — ten składnik obsługuje zarządzanie cyklem życia tej funkcji. Można go używać do zarządzania stanem różnych wersji funkcji.
    - **Konfiguracje** — ten składnik umożliwia zarządzanie, wyświetlanie i edytowanie powiązanych konfiguracji mapowania formatu i formatu ER używanych w potoku przetwarzania.
    - **Konfiguracje** — ten składnik umożliwia użytkownikom usług globalizacji, takich jak usługa fakturowania elektronicznego, zarządzanie konfiguracją odpowiedniej wersji funkcji. Z tego względu system obsługuje elastyczne konstruowanie reguł komunikacji i odpowiedzi.
    - **Środowiska** — ten składnik umożliwia użytkownikom usług globalizacji, takich jak usługa faktury elektroniczne, zarządzanie środowiskiem, w którym jest używana konfiguracja wersji funkcji. Pozwala im również udzielać autoryzacji użytkownikom, którzy będą mieli dostęp do konfiguracji wersji funkcji.
    - **Organizacje** — ten składnik umożliwia użytkownikom udostępnianie tej funkcji organizacjom zewnętrznym.
    - **Znaczniki** — ten składnik umożliwia oznaczanie funkcji, których można używać w planie globalizacji dla odwołania.

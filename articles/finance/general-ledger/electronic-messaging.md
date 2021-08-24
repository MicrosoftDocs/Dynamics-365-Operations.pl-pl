---
title: Obsługa wiadomości elektronicznych
description: Ten temat zawiera przegląd informacji o konfiguracji elektronicznego przesyłania wiadomości w Microsoft Dynamics 365 Finance.
author: liza-golub
ms.date: 06/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 191abc37b7c349aaf3c9e871fe2f1885eec9fc896271d6fac27e5caa0b0fe3b0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768346"
---
# <a name="electronic-messaging"></a>Obsługa wiadomości elektronicznych

[!include [banner](../includes/banner.md)]

Ten temat zawiera przegląd i informacje dotyczące konfiguracji funkcji **Wiadomości elektronicznych** (EM).

W ostatnim czasie władze i prawodawcy różnych krajów i regionów na całym świecie wprowadzili w życie wymagania w zakresie sprawozdawczości dla firm, które są zarejestrowane w tych krajach lub regionach. Celem tych wymagań jest możliwość uzyskiwania od tych firm danych w formie elektronicznej bezpośrednio z systemów, w których są księgowane, zapisywane i przetwarzane.

Funkcjonalność wiadomości elektroniczne w Microsoft Dynamics 365 Finance obsługuje wiele procesów elektronicznej współpracy między Finance a systemami administracji państwowej do raportowania, przesyłania i odbierania oficjalnych informacji.

Funkcje EM są zintegrowane z modułem **raportowania elektronicznego** (ER). Dlatego należy skonfigurować formaty ER dla wiadomości elektronicznych. Aby uzyskać więcej informacji, zobacz [Raportowanie elektroniczne (ER)](/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

## <a name="basic-concepts-for-em-functionality"></a>Podstawowe pojęcia dotyczące funkcjonalności EM

Funkcja EM opiera się na następujących jednostkach:

- **Wiadomość elektroniczna** — Raport lub deklaracja, która powinna być zgłoszona lub przekazana wewnętrznie, np. raport wysyłany do urzędu skarbowego.
- **Elementy wiadomości elektronicznych** — rekordy, które powinny być uwzględnione w komunikacie o błędzie.
- **Przetwarzanie wiadomości elektronicznych** — łańcuch akcji, który powinien zostać uruchomiony, aby zebrać wymagane dane, wygenerować raporty, przechowywać dane w magazynie obiektów Azure Blob, przekazywać raporty poza systemem, aktualizować bazę danych na podstawie uzyskanych informacji. Akcje w łańcuchu mogą być połączone albo odłączone.

Poniższa ilustracja przedstawia przepływ danych dla EM.

![Obsługa wiadomości elektronicznych: przepływ danych.](media/electronic-messaging-data-flow.png)

## <a name="scenarios-supported-by-the-em-functionality"></a>Scenariusze obsługiwane przez funkcję EM

Funkcja EM obsługuje następujące scenariusze:

- Ręczne tworzenie wiadomości i generowanie raportów, które opierają się na skojarzonych formatach eksportowania ER różnego typu. Typy te obejmują Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, tekst i Microsoft Word.
- Automatyczne tworzy i przetwarza wiadomości na podstawie żądanych informacji i otrzymanych z urzędu za pośrednictwem skojarzonego formatu importu ER.
- Gromadzenie i przetwarzanie informacji ze źródła danych jako elementów wiadomości. Źródło danych jest tabelą rozwiązania Finance.
- Przechowuj dodatkowe informacje i oceniaj różne wartości poprzez wywołanie specjalnie zdefiniowanych wykonywalnych klas w odniesieniu do wiadomości lub elementów wiadomości.
- Agregacja informacji zbieranych w elementach wiadomości, podział informacji według wiadomości i generowanie reportów w skojarzonych formatach eksportowania ER.
- Przekazywanie raportów generowanych do usługi sieci web przy użyciu informacji o zabezpieczeniach przechowywanych w Azure Key Vault.
- Uzyskiwanie odpowiedzi z usługi sieci web, interpretowanie odpowiedzi i aktualizowanie danych w Finance w razie potrzeby.
- Przechowywanie i przeglądanie wszystkich generowanych raportów.
- Przechowywanie i przeglądanie wszystkich informacji dziennika powiązanych z działaniami, które są uruchamiane dla wiadomości lub elementu wiadomości.
- Kontrolowanie przetwarzania za pomocą różnych stanów wiadomości i stanów elementu wiadomości.

## <a name="country-specific-regulatory-features-supported-by-the-em-functionality"></a>Specyficzne dla danego kraju funkcje regulacyjne obsługiwane przez funkcję EM

Poniższa tabela zawiera informacje o niektórych funkcjach regulacyjnych specyficznych dla danego kraju, które są obsługiwane przez funkcje EM.

| Kraj     | Nazwa funkcji | Funkcja nagrywania demo |
|-------------|--------------|------------------------|
| Hiszpania       | [Natychmiastowe dostarczenie informacji na temat podatku VAT (Suministro Inmediato de Información del IVA, SII)](../localizations/emea-esp-sii.md) | |
| Węgry     | [System fakturowania online](../localizations/emea-hun-online-invoicing.md) | |
| Wielka Brytania | [Making Tax Digital (MTD) – składanie deklaracji VAT](../localizations/emea-gbr-mtd-vat-integration.md) | [Finance and Operations: Podatek cyfrowy w Wielkiej Brytanii - Deklaracja VAT w Dynamics 365](https://community.dynamics.com/365/b/techtalks/posts/finance-and-operations-uk-digital-tax-vat-declaration-in-dynamics-365) |
| Litwa   | [Raportowanie i.SAF](../localizations/emea-ltu-isaf.md) | |
| Polska      | [Deklaracja VAT z rejestrami (JPK_V7M, VDEK)](../localizations/emea-pol-vdek.md) | [Dynamics 365 Finance: Rejestry kontroli VAT SAF/JPK](https://community.dynamics.com/365/b/techtalks/posts/dynamics-365-finance-saf-jpk-vat-audit-registers-june-4-2020) |
| Holandia | [Deklaracja VAT w Holandii](../localizations/emea-nl-vat-declaration-netherlands.md) | |
| Czechy | [Deklaracja VAT](../localizations/emea-cze-vat-declaration-tax-declaration-model.md) | |
| Brazylia      | [SPED-Reinf](../localizations/latam-bra-sped-reinf-overview.md) | |
| Rosja      | [Deklaracja VAT](../localizations/rus-vat-declaration.md) | |
| Rosja      | [Sprawozdawczość księgowa w formacie elektronicznym](../localizations/rus-accounting-reporting.md) | |
| Rosja      | [Deklaracja podatku dochodowego](../localizations/rus-profit-tax-declaration.md) | |
| Rosja      | [Deklaracja szacowanego podatku](../localizations/rus-assessed-tax-declaration.md) | |
| Rosja      | [Deklaracja podatku transportowego](../localizations/rus-transport-tax-declaration.md) | |
| Rosja      | [Deklaracja podatku gruntowego](../localizations/rus-land-tax-declaration.md) | |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]


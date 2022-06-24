---
title: Księgowanie odchylenia kosztów standardowych
description: Ten artykuł zawiera informacje o tworzeniu profili delegowania dla standardowego kosztorysowania.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: e7b2d04f32b75dbd1354b3ef74a41ea1b6469c8a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894885"
---
# <a name="standard-cost-variance-posting"></a>Księgowanie odchylenia kosztów standardowych

Kiedy używasz standardowego rachunku kosztów dla jednego lub więcej produktów w swojej organizacji, musisz skonfigurować [warunki wstępne dla standardowego rachunku kosztów](/supply-chain/cost-management/prerequisites-standard-costs.md). Ten artykuł wyjaśnia konta księgowe, które są wymagane w kroku 3 warunków wstępnych „Przydziel konta księgi głównej do księgowania pozycji, które są związane ze standardowymi odchyleniami kosztów”.

Różne rodzaje odchylenia mogą wystąpić dla zamówień zakupu i produkcji. Przykłady odchylenia produkcji znajdziesz w części [Wspólne źródła odchylenia produkcji](/supply-chain/cost-management/common-sources-of-production-variances.md). Odchylenia cenowe w zamówieniu zakupu występują wtedy, gdy używasz kosztu standardowego dla zakupionej pozycji i występuje różnica między kosztem standardowym produktu a kwotą zafakturowaną na zamówieniu zakupu.

## <a name="sample-posting-profile-configuration"></a>Przykładowa konfiguracja profilu księgowania

Poniższa tabela przedstawia przykłady domyślnych typów postów. Zawiera przykładowe konta główne i opisy.

- „Uznanie/kredyt?” Kolumna wskazuje, czy transakcja jest obciążeniem czy uznaniem. W niektórych przypadkach transakcje mogą być zarówno obciążające, jak i uznaniowe.
- Kolumna Konto rozliczeniowe wskazuje typ księgowania jako konto rozliczeniowe. Innymi słowy, kwota zaksięgowana na tym koncie jest automatycznie odwracana w momencie zaksięgowania późniejszej transakcji.
- Kolumna "P/F" wskazuje typ księgowania. „P” oznacza księgowanie fizyczne, a „F” oznacza księgowanie finansowe.
- Kolumna "Wykonaj" wskazuje, czy konto główne dla danego typu postu jest zazwyczaj takie samo jak konto główne dla innego typu postu. W szczególności wskazuje typ księgowania, który jest zazwyczaj używany.

> [!NOTE]
> Główne konta i nazwy głównych kont w tabeli są propozycjami. Zaleca się, aby współpracować z księgowym, aby ustalić najlepszą konfigurację dla potrzeb firmy.

| Typ księgowania | Przykład konta głównego | Przykład nazwy konta głównego | Typ konta | Uznanie/kredyt? | Konto rozliczeniowe | P/F | Śledzenie | Opis |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-----|--------|-------------|
| Odchylenie cen zakupu | 510310 | Odchylenie cen zakupu | Wydatek | Lub | Nie | P | Nie dotyczy | To konto jest używane, gdy występuje różnica między ceną zakupu a kosztem standardowym na zamówieniu zakupu. |
| Przeszacowanie kosztów magazynowych | 510330 | Przeszacowanie kosztów magazynowych | Wydatek | Lub | Nie | P | Nie dotyczy | To konto jest używane, gdy nowa wersja kalkulacji kosztów jest aktywowana dla pozycji kosztu standardowego w celu przeszacowania wartości zapasów na stanie. |
| Odchylenie zmiany kosztu | 510320 | Odchylenie zmiany kosztu | Wydatek | Lub | Nie | P | Nie dotyczy | To konto jest używane, gdy występują różnice w standardowych kosztach pomiędzy poszczególnymi zakładami lub gdy zwracany jest produkt, a pomiędzy pierwotnym standardowym kosztem a aktualnym standardowym kosztem produktu zachodzi zmiana. |
| Odchylenie rozmiaru partii produkcji | 510370 | Odchylenie rozmiaru partii produkcji | Wydatek | Lub | Nie | P | Nie dotyczy | To konto jest używane, gdy występują różnice między podstawą kalkulacji zatwierdzenia listy składowej (BOM) a rzeczywistą ilością do kalkulacji kosztów zlecenia produkcyjnego. |
| Rozbieżność cen produkcji | 510340 | Rozbieżność cen produkcji | Wydatek | Lub | Nie | P | Nie dotyczy | To konto jest używane, gdy występują różnice cenowe między kosztem szacunkowym a rzeczywistym dla zlecenia produkcyjnego. |
| Odchylenie ilości produkcji | 510350 | Odchylenie ilości produkcji | Wydatek | Lub | Nie | P | Nie dotyczy | To konto jest używane, gdy występują różnice ilościowe między kosztami szacunkowymi a rzeczywistymi dla danego zlecenia produkcyjnego. |
| Odchylenie podstawiania produkcji | 510360 | Odchylenie podstawiania produkcji | Wydatek | Lub | Nie | P | Nie dotyczy | To konto jest używane, gdy na zleceniu produkcyjnym pojawia się nieoczekiwana konsumpcja. |
| Odchylenie zaokrąglania | 618160 | Zaokrąglenie różnicy | Wydatek | Lub | Nie | P | Nie dotyczy | To konto jest używane, gdy występuje różnica w zaokrągleniu przy obliczaniu kosztów produkcji w stosunku do kosztów standardowych. |

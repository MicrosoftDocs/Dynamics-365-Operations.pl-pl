---
title: Konfigurowanie zabezpieczeń pakietu zawartości usługi Power BI Analiza rachunku kosztów
description: W tym temacie wyjaśniono, jak można rozpowszechnić zabezpieczenia na poziomie dostępu w module Rachunek kosztów do zabezpieczeń na poziomie wierszy w usłudze Microsoft Power BI. Ta funkcja pomaga zagwarantować, że użytkownicy widzą tylko dane usługi Power BI, do których mają dostęp.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 04ff1523f7b05fe8398513e913702b0f3c7c354c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682196"
---
# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Konfigurowanie zabezpieczeń pakietu zawartości usługi Power BI Analiza rachunku kosztów

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak można rozpowszechnić zabezpieczenia na poziomie dostępu w module Rachunek kosztów do zabezpieczeń na poziomie wierszy w usłudze Microsoft Power BI. Ta funkcja pomaga zagwarantować, że użytkownicy widzą tylko dane usługi Power BI, do których mają dostęp.

## <a name="overview"></a>Przegląd

Pakiet zawartości **Analiza rachunku kosztów** dla usługi Microsoft Power BI używa zabezpieczeń na poziomie wierszy z usługi Power BI, aby ograniczyć dostęp użytkownikom. Zabezpieczenia są oparte na hierarchii organizacyjnej na poziomie dostępu skonfigurowanej w oknie Parametry rachunku kosztów. Aby uzyskać więcej informacji na temat pakietu zawartości **Analiza rachunku kosztów** dla usługi Power BI, zobacz [Pakiet zawartości usługi Power BI Analiza rachunku kosztów](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Konfiguracja
Aby rozpowszechnić zabezpieczenia na poziomie dostępu do usługi Power BI, właściciel pakietu zawartości usługi Power BI musi wykonać czynności opisane poniżej.

> [!NOTE]
> Użytkownik, który publikuje pakiet zawartości usługi Power BI **Analiza rachunku kosztów**, automatycznie staje się właścicielem. Tylko właściciel może konfigurować zabezpieczenia w usłudze Power BI. Dodatkowo dopóki właściciel nie doda innych użytkowników w witrynie PowerBI.com, nikt oprócz niego nie będzie widział żadnych danych w pakiecie zawartości **Analiza rachunku kosztów** usługi Power BI.

1. Opublikuj plik definicji do usługi Power BI.
2. Zaloguj się w witrynie PowerBI.com.
3. Znajdź zestaw danych pakietu zawartości usługi Power BI **Analiza rachunku kosztów**.
4. Otwórz stronę zabezpieczeń.

    ![Otwieranie strony zabezpieczeń](./media/CA-picture-1.png)

5. Rola **Kontroler obiektów kosztów** jest już utworzona. Dodaj innych członków będących częścią hierarchii organizacyjnej na poziomie dostępu zatytułowanej Kontrola kosztów.

    ![Dodawanie członków](./media/CA-picture-2.png)

Użytkownicy, którzy zostaną dodani do roli **Kontroler obiektów kosztów**, będą widzieć tylko dane, które mają prawo zobaczyć zgodnie z definicją w hierarchii organizacyjnej na poziomie dostępu zatytułowanej Rachunek kosztów.

> [!NOTE]
> Zabezpieczenia na poziomie wierszy dotyczą kafelków i raportów, które zostały osadzone z usługi Power BI.

## <a name="updating-security"></a>Aktualizowanie zabezpieczeń
Jeśli w module Rachunek kosztów dokonano aktualizacji zabezpieczeń na poziomie dostępu, a chcesz, aby usługa Power BI uwzględniała te aktualizacje, należy zaktualizować magazyn jednostek pakietu zawartości usługi Power BI **Analiza rachunku kosztów**. Po wykonaniu aktualizacji magazynu jednostek należy zaktualizować artefakty w usłudze PowerBI.com. Aby uzyskać więcej informacji na temat sposobu aktualizowania magazynu jednostek, zobacz [Integracja usługi Power BI z magazynem jednostek](power-bi-integration-entity-store.md#update-entity-store). Właściciel pakietu zawartości **Analiz rachunku kosztów** dla usługi Power BI musi również zaktualizować magazyn jednostek, jeśli nowym użytkownikom zostanie przyznany dostęp do hierarchii organizacyjnej. Ponadto właściciel musi dodać nowych użytkowników do roli **Kontroler obiektów kosztów** w witrynie PowerBI.com, tak aby zabezpieczenia na poziomie wierszy były do nich stosowane.

## <a name="disabling-security"></a>Wyłączanie zabezpieczeń
Zakładamy, że Twoja organizacja chce ograniczyć dostęp do danych. Jeśli z jakiegoś powodu parametry zabezpieczeń zostaną wyłączone podczas używania modułu Rachunek kosztów, właściciel musi dodać użytkowników do roli **Księgowy kosztów** w usłudze Power BI. Jeśli zmienisz zabezpieczenie ze stanu włączenia na stan wyłączenia, dobrym rozwiązaniem jest usunięcie użytkowników z roli **Kontroler obiektów kosztów**. I odwrotnie, jeśli ponownie włączyć zabezpieczenia. Użytkownicy mogą należeć do obu ról. Wspólny dostęp stanowi część wspólną uprawnień obu ról. W odniesieniu do pakietu zawartości **Analiza rachunku kosztów** dla usługi Power BI użytkownicy posiadający wspólny dostęp mają nieograniczony dostęp do danych. Jeśli Twoim celem jest stosowanie ograniczonego dostępu, użytkownicy muszą być przypisani tylko do roli **Kontroler obiektów kosztów**. Te aktualizacje zabezpieczeń na poziomie wierszy zaczynają obowiązywać natychmiast. Odnośni użytkownicy powinni odświeżyć swoje przeglądarki.

## <a name="additional-resources"></a>Dodatkowe zasoby
Aby dowiedzieć się więcej na temat zabezpieczeń na poziomie wierszy w usłudze Power BI, zobacz [Zarządzanie zabezpieczeniami modelu w usłudze Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-rls/#manage-security-on-your-model).

---
title: "Ustaw zabezpieczenia zawartości Power BI analizy rachunku kosztów"
description: "W tym temacie wyjaśniono, jak można propagować zabezpieczeń poziom dostępu w rachunku kosztów do zabezpieczenia na poziomie wiersza w Microsoft Power BI. Ta funkcja pomaga zagwarantować, że użytkownicy widzą tylko danych BI uzyska dostęp do."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 1e42622e7621c645d7eda3299f78c34c7e41a251
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Ustaw zabezpieczenia zawartości Power BI analizy rachunku kosztów

W tym temacie wyjaśniono, jak można propagować zabezpieczeń poziom dostępu w rachunku kosztów do zabezpieczenia na poziomie wiersza w Microsoft Power BI. Ta funkcja pomaga zagwarantować, że użytkownicy widzą tylko danych BI uzyska dostęp do.

<a name="overview"></a>Przegląd
--------

**Analizy rachunku kosztów** zawartości Microsoft Power BI używa zabezpieczenia na poziomie wiersza Power BI ograniczyć dostęp użytkownika. Zabezpieczenia są oparte na hierarchii organizacyjnej poziom dostępu, ustawionej w parametrach modułu Rachunek kosztów. Aby uzyskać więcej informacji na temat **analizy rachunku kosztów** Power BI zawartości, zobacz [rachunku kosztów analizy zawartości Power BI](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Konfiguracja
Propagowanie poziom dostępu zabezpieczeń do Power BI, właściciel zawartości BI zasilania należy wykonać następujące kroki. **Uwaga:** użytkownika, który publikuje **analizy rachunku kosztów** Power BI zawartości automatycznie staje się właścicielem. Tylko właściciel można ustawić zabezpieczenia w BI zasilania. Dodatkowo, aż do właściciela dodaje innych użytkowników na PowerBI.com, nikt oprócz właściciela zobaczyć wszystkie dane w **analizy rachunku kosztów** Power BI zawartości.

1.  Opublikować plik definicji Power BI.
2.  Zaloguj się do PowerBI.com.
3.  Znajdowanie zestawu danych dla **analizy rachunku kosztów** Power BI zawartości.
4.  Otwórz stronę Zabezpieczenia. 

    [![Otwarcie strony zabezpieczeń](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)

5.  **Kontrolera obiektu kosztów** roli jest już utworzony. Dodawanie innych członków, którzy są częścią hierarchii organizacyjnej poziomu dostępu do rachunku kosztów. 

    [![Dodawanie członków](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)

Użytkownicy, którzy zostaną dodani do **kontrolera obiektu kosztów** rolę zobaczy tylko dane, które mogą zobaczyć, zgodnie z definicją w hierarchii organizacyjnej poziomu dostępu do rachunku kosztów. **Uwaga:** zabezpieczeń na poziomie wierszy dotyczy płytek i raporty w programie Microsoft Dynamics 365 dla operacji, które są osadzone z Power BI.

## <a name="updating-security"></a>Aktualizacja zabezpieczeń
Uaktualnienia odnoszą się do zabezpieczenia na poziomie dostępu w rachunku kosztów, a chcesz BI zasilania, aby odzwierciedlić te aktualizacje, musisz zaktualizować magazynu jednostki dla **analizy rachunku kosztów** Power BI zawartości. Po zakończeniu aktualizacji magazynu jednostki z 365 Dynamics dla operacji, należy zaktualizować artefaktów na PowerBI.com. Aby uzyskać więcej informacji na temat sposobu wykonania aktualizacji magazynu encji, zobacz [aktualizacji jednostki magazynu](power-bi-integration-entity-store.md#update-entity-store). Właściciel **analizy rachunku kosztów** Power BI zawartości musisz zrobić także aktualizacji magazynu jednostki, jeśli nowi użytkownicy uzyskają dostęp do hierarchii organizacyjnej. Ponadto właściciel należy dodać nowych użytkowników, aby **kontrolera obiektu kosztów** roli na PowerBI.com, tak że zabezpieczenia na poziomie wiersza jest stosowany dla nich.

## <a name="disabling-security"></a>Wyłączanie zabezpieczeń
Zakładamy, że organizacja chce ograniczyć dostęp do danych. Jeśli z jakiegoś powodu parametrów zabezpieczeń są wyłączone po uruchomieniu rachunku kosztów, właściciel należy dodać użytkowników do **księgowy kosztów** rolę w BI zasilania w zamian. Jeśli zmienisz zabezpieczeń z stanie włączonym na wyłączony, to dobry pomysł, aby usunąć użytkowników z **kontrolera obiektu kosztów** roli. I odwrotnie, jeśli ponownie włączyć zabezpieczenia. Użytkownicy mogą należeć do obu ról. Wspólny dostęp jest Unia obu ról. W odniesieniu do **analizy rachunku kosztów** Power BI zawartości, użytkownicy, którzy mają dostęp do wspólnego mają nieograniczony dostęp do danych. Jeśli celem jest aby zastosować ograniczony dostęp, użytkownicy muszą być przypisani tylko do **kontrolera obiektu kosztów** roli. Te aktualizacje zabezpieczeń na poziomie wiersza zaczynają obowiązywać natychmiast. Użytkowników należy odświeżyć swoich przeglądarek.

## <a name="additional-resources"></a>Dodatkowe zasoby
Aby dowiedzieć się więcej na temat zabezpieczeń na poziomie wiersza BI zasilania, zobacz [Zarządzanie zabezpieczeniami na model w Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).



---
title: Obsługa certyfikacji dostawcy
description: W tym temacie opisano kroki, których dostawcy mogą używać do obsługi certyfikacji za pomocą obszaru współpracy z dostawcami.
author: v-kiarnd
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 932b8bc2982a7c38404ff4203fce7fb65c1182d4490d2aad5a6d78fd809ec768
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736119"
---
# <a name="maintain-vendor-certification"></a>Obsługa certyfikacji dostawcy

[!include [banner](../includes/banner.md)]

W tym temacie opisano kroki, których dostawcy mogą używać do obsługi certyfikacji za pomocą **obszaru współpracy z dostawcami**. Przykładami mogą być certyfikaty Woman Business Enterprise (WBE) lub Leadership in Energy and Environment Design (LEED). Dostawcy muszą wprowadzać informacje o certyfikacjach w obszarze roboczym **Informacje o dostawcy**. W tym miejscu dostawcy będą wybierać opcję **Więcej szczegółów**, a następnie **Certyfikaty**.

## <a name="turn-on-the-vendor-certification-feature"></a>Włączanie funkcji certyfikacji dostawcy

Aby móc używać tej funkcji, należy ją włączyć w systemie. Administratorzy mogą skorzystać ze strony [Zarządzania funkcją](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), aby sprawdzić stan funkcji i włączyć ją w razie potrzeby. W obszarze roboczym **Zarządzanie funkcjami** ta funkcja widnieje jako:

- **Moduł** - *Rozrachunki z dostawcami*
- **Nazwa funkcji** - *Włącz zarządzanie certyfikatami współpracy z dostawcami*

## <a name="add-a-new-certification"></a>Dodaj nowy certyfikat

Aby dodać nowy certyfikat, wybierz przycisk **Dodaj**, który znajduje się nad siatką **Certyfikat** w obszarze roboczym **Informacje o dostawcy**. Podaj poniższe informacje:

- Numer certyfikacji
- Typ certyfikacji
- Urząd certyfikacji
- Data certyfikacji
- Kwota zobowiązania, jeśli ma zastosowanie
- Data obowiązywania
- Data wygaśnięcia
- Komentarze, opcjonalne

Jeśli istnieją dokumenty związane z danym certyfikatem, można je dołączyć, wybierając przycisk **Dokument**.

Certyfikaty wprowadzane na tej stronie przez dostawców zostaną przypisane do źródła „Dostawca”. Możesz wprowadzić informacje o certyfikacie w imieniu dostawcy w ramach kont bankowych dostawcy. Informacje będą wyświetlane w tym miejscu, a źródło będzie wyświetlane jako **Odbiorca**.

Dostawcy w razie potrzeby mogą edytować lub usuwać certyfikaty.

## <a name="vendor-collaboration-generated-certification-records"></a>W portalu współpracy z dostawcami wygenerowano rekordy certyfikacji

Po dodaniu informacji dotyczących certyfikacji przez dostawcę te informacje będą widoczne na stronie **certyfikacji wygenerowanej w portalu współpracy z dostawcami**. Aby otworzyć tę stronę, wybierz opcje **Rozrachunki z dostawcami > Informacje > Raporty dostawców > Certyfikacje wygenerowane w portalu współpracy z dostawcami**. Domyślnie widoczne są wszystkie nowe lub zmodyfikowane rekordy certyfikacji. Ler rozrachunków z dostawcami może wyświetlać zmiany i sprawdzać poprawność informacji w procesie potwierdzania ich poprawności. Po potwierdzeniu informacji można wybrać rekord certyfikacji wymieniony na stronie i zaznaczyć go jako przejętego. Oznaczenie rekordu jako przejętego spowoduje usunięcie go z listy domyślnej.

Wszystkie zmiany certyfikacji są widoczne na stronie **Certyfikacji wygenerowanej w portalu współpracy z dostawcami**. Jeśli zmiana nie jest wyświetlana na stronie, można ją wyświetlić, przesunąc filtry dla konta dostawcy, zakresu dat efektywnych lub zdecydować, czy uwzględnić informacje dotyczące przeglądanych zmian certyfikacji.


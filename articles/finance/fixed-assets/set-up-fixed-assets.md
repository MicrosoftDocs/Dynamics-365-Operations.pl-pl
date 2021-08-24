---
title: Konfigurowanie środków trwałych
description: W tym temacie omówiono konfigurację modułu Środki trwałe.
author: moaamer
ms.date: 06/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13771
ms.assetid: 8be64197-fea1-4a34-8af2-d939919c28b1
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 572d104bbc7024da1ea4b219fd3f544f36a88ccddcf1aa5d18065e2e08b93bfa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754225"
---
# <a name="set-up-fixed-assets"></a>Konfigurowanie środków trwałych

[!include [banner](../includes/banner.md)]

W tym temacie omówiono konfigurację modułu **Środki trwałe**. 

Parametry kontrolują ogólne zachowanie w module Środki trwałe. Grupy środków trwałych umożliwiają grupowanie składników aktywów oraz określanie domyślnych atrybutów dla każdego składnika aktywów przypisanego do grupy. Grupom środków trwałych są przypisywane księgi. Księgi śledzą wartości finansowe środków trwałych w czasie przy użyciu konfiguracji amortyzacji, która jest zdefiniowana w profilu amortyzacji.

Środki trwałe przypisuje się do grupy podczas ich tworzenia. Domyślnie księgi przypisane do grupy środków trwałych są następnie przypisywane do środka trwałego. Księgi skonfigurowane do księgowania w księdze głównej są skojarzone z profilem księgowania. Konta księgowe są określane dla każdej księgi w profilu księgowania i używane podczas księgowania transakcji na środkach trwałych.

![Składniki funkcjonalności środków trwałych.](./media/FAComponents_Updated.png)

## <a name="depreciation-profiles"></a>Profile amortyzacji

Najpierw należy skonfigurować profile amortyzacji. W profilu amortyzacji określasz sposób amortyzowania wartości składnika aktywów w czasie. Należy zdefiniować metodę amortyzacji, rok amortyzacji (kalendarzowy lub obrachunkowy) i częstotliwość amortyzacji. Aby uzyskać więcej informacji, zobacz [Konfigurowanie i tworzenie profili amortyzacji](tasks/set-up-depreciation-profiles.md).

## <a name="books"></a>Księgi

Po skonfigurowaniu profili amortyzacji należy utworzyć księgi wymagane dla składników aktywów. Każda księga śledzi niezależny finansowy cykl życia składnika aktywów. Księgi można skonfigurować w taki sposób, aby powodowały księgowanie powiązanych transakcji w księdze głównej. Ta konfiguracja jest ustawieniem domyślnym, ponieważ zwykle stosuje się ją w sprawozdawczości finansowej w przedsiębiorstwach. Księgi, które nie powodują księgowania w księdze głównej, księgują tylko do podrzędnej księgi środków trwałych i zazwyczaj są używane na potrzeby sprawozdawczości podatkowej.

Każda księga ma przypisany główny profil amortyzacji. Księgi mają również alternatywne (przełączane) profile amortyzacji, jeśli pozwala na to typ profilu. Aby automatycznie uwzględniać księgę środków trwałych w sesjach księgowania amortyzacji, należy włączyć opcję **Oblicz amortyzację**. Jeśli ta opcja nie jest włączona dla składnika aktywów, propozycja amortyzacji pomija ten składnik.

Można również skonfigurować księgi pochodne. Wskazane transakcje pochodne są księgowane w księgach pochodnych jako dokładne kopie transakcji podstawowych. W związku z tym transakcje pochodne są zazwyczaj konfigurowane dla transakcji nabycia i likwidacji, a nie dla transakcji amortyzacji. Aby uzyskać więcej informacji, zobacz [Konfigurowanie modeli ewidencji](tasks/set-up-value-models.md).

Opcja na stronie **Parametry środków trwałych** umożliwia włączanie i wyłączanie funkcji blokowania. Tę funkcję podglądu można włączyć w **Obszarze roboczym zarządzanie funkcjami**.

## <a name="fixed-asset-posting-profiles"></a>Profile księgowania środków trwałych

Po skonfigurowaniu ksiąg można utworzyć profil księgowania. Profil księgowania musi być zdefiniowany dla księgi, ale można go również zdefiniować na bardziej szczegółowym poziomie. Na przykład można zdefiniować profil księgowania dla kombinacji księgi i grupy środków trwałych, a nawet dla pojedynczej księgi środków trwałych. Domyślnie dla transakcji na środkach trwałych są używane już zdefiniowane konta księgowe.

Należy zdefiniować konta księgowe, które mają być używane podczas procesów likwidacji — zarówno likwidacji sprzedaży, jak i likwidacji odpadków. W momencie likwidacji transakcje na środkach trwałych, które zostały wcześniej zaksięgowane, są wycofywane z oryginalnych kont, a kwoty netto są przenoszone do odpowiedniego konta zysków i strat z likwidacji środków trwałych. Aby zagwarantować poprawne wycofywanie transakcji, należy skonfigurować konta dla wszystkich typów transakcji używanych w firmie. Kontem głównym powinno być oryginalne konto główne ustawione w profilu księgowania dla tego typu transakcji, a kontem przeciwstawnym powinno być konto zysków i strat z likwidacji. Wyjątkiem jest wartość księgowa netto. W takim przypadku kontem głównym i kontem przeciwstawnym powinno być konto zysków i strat z likwidacji. Aby uzyskać więcej informacji, zobacz [Konfigurowanie profili księgowania środków trwałych](tasks/set-up-fixed-asset-posting-profiles.md).

## <a name="fixed-asset-groups"></a>Grupy środków trwałych

Pole **Grupa środków trwałych** jest jedynym polem wymaganym podczas tworzenia środka trwałego. Wartość tego pola decyduje o wartości domyślnej kilku pól informacyjnych tego składnika aktywów. Księgi są skonfigurowane w taki sposób, że księga domyślna jest przypisana do każdego składnika aktywów w grupie. W ten sposób atrybuty konfigurowane dla ksiąg mogą być specyficzne dla grupy składników aktywów. Do tych atrybutów należą okres użytkowania i konwencja amortyzacji.

Można również zdefiniować specjalne odpisy amortyzacyjne lub podwyższenie amortyzacji dla określonych kombinacji grupy środków trwałych i księgi. Specjalnemu odpisowi amortyzacyjnemu należy przypisać priorytet, co pozwoli określić kolejność obliczania odpisów w razie przypisania wielu odpisów do księgi. Aby uzyskać więcej informacji, zobacz [Ustawianie grup środków trwałych](tasks/set-up-fixed-asset-groups.md).

## <a name="journal-names"></a>Nazwy arkuszy

Na stronie **Nazwy arkuszy** należy utworzyć nazwy arkuszy, które mają być używane w arkuszu środków trwałych. W polu **Typ arkusza** należy ustawić wartość **Księgowanie środków trwałych**. Wypełnij pole **Seria załączników**, tak aby w arkuszu środków trwałych były używane nazwy arkuszy. W arkuszach środków trwałych nie powinno się używać ustawienia **Tylko jeden numer załącznika**, ponieważ unikatowy numer załącznika jest wymagany przez różne zautomatyzowane procesy, na przykład przenoszenia i rozdzielania.

## <a name="fixed-asset-parameters"></a>Parametry środków trwałych

Ostatnim krokiem jest zaktualizowanie parametrów środków trwałych.

Pole **Próg kapitalizacji** określa składniki aktywów, które są amortyzowane. Jeśli jako środek trwały zostanie wybrany wiersz zakupu, ale nie spełnia on określonego progu kapitalizacji, środek trwały nadal zostanie utworzony lub zaktualizowany, ale opcja **Oblicz amortyzację** otrzymuje wartość **No**. W związku z tym ten składnik aktywów nie będzie automatycznie amortyzowany w ramach propozycji amortyzacji.

Inną ważną opcją jest **Automatyczne tworzenie kwot korekty amortyzacji przy likwidacji**. Jeśli zostanie wybrana dla niej wartość **Tak**, amortyzacja składnika aktywów jest automatycznie korygowana zgodnie z ustawieniami amortyzacji w momencie likwidacji składnika. Inna opcja umożliwia odjęcie rabatów gotówkowych od kwoty nabycia w przypadku nabywania środków trwałych za pomocą faktury od dostawcy.

Parametr **Zablokuj księgi środków w dzienniku amortyzacji** pozwala na zablokowanie ksiąg środków w dzienniku amortyzacji. Podczas księgowania transakcji amortyzacji system sprawdzi, czy ta sama księga środka trwałego nie została dodana do więcej niż jednego dziennika amortyzacji. Jeśli tak się stało, księga aktywów zostanie zablokowana, a księgowanie zostanie wstrzymane. Jeżeli identyfikator księgi aktywów znajduje się w zablokowanym dzienniku, zostanie on automatycznie odblokowany po zakończeniu księgowania dla pierwotnego dziennika. Można również odblokować dziennik ręcznie. 

Na skróconej karcie **Zamówienia zakupu** można skonfigurować sposób tworzenia środków trwałych w ramach procesu zakupów. Pierwszą opcją jest **Zezwalaj na nabywanie środków trwałych z zakupów**. Jeśli zostanie w niej wybrana wartość **Tak**, nabycie środka trwałego następuje podczas księgowania faktury. Jeśli zostanie wybrana wartość **Nie**, nadal można umieścić środek trwały w zamówieniu zakupu i na fakturze, ale nabycie nie zostanie zaksięgowane. Księgowanie musi zostać przeprowadzone jako oddzielny krok z arkusza środków trwałych. Opcja **Utwórz środek trwały podczas księgowania dokumentu przyjęcia produktów lub faktury** pozwala utworzyć nowy składnik aktywów „na bieżąco” podczas księgowania, dzięki czemu nie musi on być skonfigurowany jako środek trwały przed transakcją. Ostatnia opcja, **Sprawdź, czy podczas wprowadzania wiersza zostaną utworzone środki trwałe**, ma zastosowanie tylko do zapotrzebowań na zakup.

Można skonfigurować kody przyczyny, aby były wymagane przy modyfikacjach środków trwałych lub określonych transakcjach na środkach trwałych.

Wreszcie na karcie **Sekwencje numerów** należy określić numerację środków trwałych. Numeracja w polu **Środek trwały** może zostać zastąpiona przez numerację z pola **Grupa środków trwałych**, jeśli została określona.

Aby uzyskać więcej informacji, zobacz [Tworzenie środka trwałego](tasks/create-fixed-asset.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

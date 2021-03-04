---
title: Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji
description: W tym temacie opisano sposób używania szablonów pracy i dyrektyw lokalizacji do określania, jak i gdzie praca jest wykonywana w magazynie.
author: perlynne
manager: tfehr
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 21f6240b247433c7448a9aa5543996f19b3a25dd
ms.sourcegitcommit: 4bf5ae2f2f144a28e431ed574c7e8438dc5935de
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2020
ms.locfileid: "4517435"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Kontrola pracy magazynu za pomocą szablonów pracy i dyrektyw lokalizacji

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób używania szablonów pracy i dyrektyw lokalizacji do określania, jak i gdzie praca jest wykonywana w magazynie.

Instrukcje otrzymywane przez pracowników magazynu na urządzeniu przenośnym są określane w szablonach pracy konfigurowanych w Dynamics 365 Supply Chain Management w celu zdefiniowania różnych procesów i zadań magazynowych. Szablony pracy określają, jak wykonywana jest praca dla każdego procesu magazynowego. Połączenie dyrektywy lokalizacji z szablonem pracy pomaga zagwarantować, że praca ma miejsce w określonych obszarach fizycznych magazynów.

## <a name="work-templates"></a>Szablony pracy

Strona **Szablony pracy** pozwala zdefiniować operacje pracy, które muszą być wykonane w magazynie. Zwykle operacje pracy w magazynie składają się z dwóch działań: pracownik magazynu odbiera dostępny towar w lokalizacji, a następnie odkłada odebrany towar w innej lokalizacji. 

Szablony pracy składają się z nagłówka i skojarzonych z nim wierszy. Każdy szablon pracy dotyczy określonego *typu zlecenia*. Wiele typów zleceń jest skojarzonych z dokumentami źródłowymi, takimi jak zamówienia zakupu lub sprzedaży. Jednak inne typy zleceń reprezentują odrębne czynności magazynowe, takie jak inwentaryzacja ciągła. *Identyfikator puli pracy* umożliwia organizowanie pracy w grupy. 

Ustawienia w definicji nagłówka pracy mogą służyć do określania, czy ma być tworzony nowy element pracy. Można na przykład ustawić maksymalną liczbę wierszy pobrania i maksymalny oczekiwany czas pobrania. Następnie, jeśli praca dla procesu odbioru zamówienia sprzedaży przekroczy którąś z tych wartości, ta praca jest dzielona na dwa fragmenty pracy.

**Przycisk podziały nagłówka pracy** umożliwia definiowanie czasu, w którym system powinien tworzyć nowe nagłówki pracy. Na przykład, aby utworzyć nagłówek pracy dla każdego _numeru zamówienia_, w okienku akcji wybierz opcję **Edytuj kwerendę**, a następnie Dodaj pole **Numer zamówienia** na karcie **Sortowanie** w Edytorze zapytań. Pola dodawane do karty **sortowania** są dostępne do wyboru jako *pola grupowania*. Aby określić pola grupowania, wybierz opcję **podział nagłówka pracy** w okienku akcji, a następnie w przypadku każdego pola, które ma być używane jako pole grupowania, zaznacz pole wyboru w kolumnie **grupuj według tego pola**.

Wiersze pracy odpowiadają fizycznym zadaniom, które wymagane do przetworzenia pracy. Na przykład dla procesu magazynu wyjściowego może być jeden wiersz dla odbierania towarów w magazynie i inny wiersz do odkładania tych elementów w obszaru przygotowania wysyłki. Kolejny wiersz może dotyczyć odbioru towarów z obszaru przygotowania wysyłki, a jeszcze inny ładowania towarów na ciężarówkę w ramach procesu załadunkowego. Można ustawić *kod dyrektywy* w wierszach szablonu pracy. Kod dyrektywy jest połączony z dyrektywą lokalizacji i pomaga zagwarantować, że praca magazynu jest przetwarzana w odpowiednim miejscu w magazynie.

Za pomocą specjalnego zapytania można kontrolować sposób używania określonego szablonu pracy. Można na przykład można ustawić ograniczenie, aby dany szablon był używany tylko dla pracy w danym magazynie. Można też mieć kilka szablonów do tworzenia pracy dla przetwarzania wychodzących zamówień sprzedaży w zależności od źródła sprzedaży. Za pomocą pola **Numer sekwencyjny** system określa porządek oceniania dostępnych szablonów pracy. Dlatego bardzo szczegółowe zapytania dotyczące konkretnego szablonu pracy powinny mieć niski numer kolejny. Takie zapytanie jest wtedy oceniane przed innymi, które są ogólniejsze.

> [!NOTE]
> Aby zapobiec automatycznemu zastąpieniu przez system *numerów sekwencyjnych szablonów pracy* po usunięciu szablonu, Włącz *funkcję zachowywania numerów sekwencyjnych szablonów roboczych* w module [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Aby zatrzymać lub wstrzymać proces pracy, można użyć ustawienia **Zatrzymanie pracy** w wierszu pracy. W takim przypadku pracownik, który wykonuje pracę, nie będzie musiał wykonywać następnego kroku wiersza pracy. Aby przejść do następnego kroku, ten lub inny pracownik musi wybrać pracę ponownie. Można też oddzielić zadania w ramach danej pracy przy użyciu różnych *identyfikatorów klasy pracy* w wierszach szablonu pracy.

## <a name="location-directives"></a>Dyrektywy lokalizacji

Dyrektywy lokalizacji to zasady pomagające w zidentyfikowaniu lokalizacji pobrania i odłożenia do celów przesunięcia magazynowego. Na przykład w ramach transakcji zamówienia sprzedaży, dyrektywa lokalizacji określa, gdzie towary zostaną pobrane i gdzie zostaną umieszczone pobrane zapasy. Dyrektywy lokalizacji składają się z nagłówka i skojarzonych z nim wierszy. Tworzy się je na stronie **Dyrektywy lokalizacji**.

W nagłówku każda dyrektywa lokalizacji musi być skojarzona z *typem zlecenia* określającym rodzaj transakcji magazynowej, dla którego dyrektywa będzie używana, np. zamówienia sprzedaży, uzupełnienia zapasów czy pobranie surowca. *Typ pracy* określa, czy dyrektywa lokalizacji będzie używana do pobierania lub odkładania pracy czy jakiegoś innego procesu magazynu, np. liczenie czy zmiany stanu zapasów. Należy także określić *oddział* i *magazyn*. *Kod dyrektywy* określony w nagłówku może służyć do łączenia dyrektywy lokalizacji w jeden lub kilka szablonów pracy. 

W przypadku szablonów pracy można skonfigurować kwerendę do określania, kiedy dana dyrektywa lokalizacji jest używana. Na przykład można określić, że jeśli źródłem zamówienia sprzedaży jest e-commerce, zapasy muszą zostać odebrane dedykowanego obszaru w magazynie. Za pomocą pola **Numer sekwencyjny** system określa porządek oceniania dostępnych dyrektyw lokalizacji.

Wiersze dyrektywy lokalizacji określają dodatkowe ograniczenia dotyczące stosowania reguł znajdowania lokalizacji. Można określić ilość minimalną i maksymalną, do której ma się stosować dyrektywa, i można określić, że dyrektywa powinna być skojarzona z konkretną jednostką magazynową. Na przykład, jeśli jednostką miary jest paleta, tylko towary na paletach można umieścić w określonej lokalizacji. Można też określić, czy ilość może być dzielona pomiędzy wiele lokalizacji. Podobnie jak w przypadku nagłówka dyrektywy każdy wiersz dyrektywy lokalizacji ma numer kolejny, który określa porządek, w jakim wiersze są oceniane.

Dyrektywa lokalizacji ma jeden dodatkowy poziom szczegółowości: *działania dyrektywy lokalizacji*. Można określić wiele działań dyrektywy lokalizacji dla każdego wiersza. I znowu numer kolejny jest używany do określania porządku oceniania działań. Na tym poziomie można skonfigurować zapytanie do określenia sposobu znajdowania najlepszej lokalizacji w magazynie. Można też znaleźć optymalną lokalizację przy użyciu predefiniowanego ustawienia **Strategia**.

Aby uzyskać więcej informacji na temat sposobu tworzenia i konfigurowania dyrektyw lokalizacji, należy zapoznać się z tematem [Tworzenie dyrektywy lokalizacji](create-location-directive.md).

### <a name="how-location-directives-work"></a>Praca z dyrektywami lokalizacji

Dyrektywy lokalizacji określają, *gdzie* towary powinny być pobierane i *gdzie* powinny być umieszczane. System ocenia dyrektywę lokalizacji w odniesieniu do każdego wiersza pracy, a następnie wybiera lokalizację na podstawie szczegółów wiersza pracy. System najpierw odnajduje wszystkie dyrektywy lokalizacji odpowiadające określonemu wierszowi pracy (na przykład, dla prawidłowego magazynu i odpowiada kwerendzie). Umożliwia ona sekwencyjne ocenianie znalezionych dyrektyw.

> [!NOTE]
> Istnieją specjalne przypadki, w których jest wstępnie wybrana lokalizacja pobrania lub lokalizacja lokalizacji docelowej. Na przykład podczas _rejestracji zakupu_ pierwsze pobranie jest zawsze z lokalizacji, w której odbywa się rejestracja. Innym przykładem jest *Przesunięcie magazynowe według szablonu*, w którym pracownik magazynu wybiera lokalizację pobrania, a tylko lokalizacje odłożenia są dostępne w dyrektywach lokalizacji.

## <a name="additional-resources"></a>Dodatkowe zasoby

- Wideo: [Konfiguracja zarządzania magazynem — zaawansowana](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Temat pomocy: [Tworzenie dyrektyw lokalizacji](create-location-directive.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
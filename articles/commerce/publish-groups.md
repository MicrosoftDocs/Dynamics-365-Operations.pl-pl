---
title: Praca z grupami publikowania
description: W tym temacie opisano funkcję grup publikowania w aplikacji Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0a4f19af0cdf9c72add0ec18be84e36c807af9ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969883"
---
# <a name="work-with-publish-groups"></a>Praca z grupami publikowania


[!include [banner](includes/banner.md)]

W tym temacie opisano funkcję grup publikowania w aplikacji Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Witryny e-Commerce są stale aktualizowane przy użyciu nowej zawartości przez cały rok. Aktualizacje są często publikowane w partiach w przypadku dynamicznych wydarzeń typu e-Commerce, takich jak święta, sezonowe kampanie marketingowe lub promocyjne wprowadzenia produktów na rynek. Te aktualizacje często wymagają, aby grupy zawartości witryny internetowej (np. strony, obrazy, fragmenty i szablony) były przemieszczane, weryfikowane i publikowane równocześnie w ramach pojedynczej akcji.

Możliwość grupowania elementów w zestawy logiczne, które publikują elementy razem, gdzie każdy zestaw ma swój własny cykl życia, oferuje wiele zalet dla autorów witryny. W usłudze Commerce te zestawy logiczne są nazywane grupami publikowania. Pozwalają one autorom witryn śledzić zestawy aktualizacji jako własne jednostki konfigurowalne z możliwością publikowania i testowania.

Autorzy mogą wyświetlać podgląd aktualizacji w przejściowej grupie publikowania bez wpływu na aktywną witrynę lub inne niezależne grupy publikowania. Autorzy mogą następnie zaplanować akcję publikowania, aby jednocześnie opublikować wszystkie elementy w grupie publikowania w witrynie działającej na żywo. Możliwość grupowania, podglądu i planowania aktualizacji publikowania jest ważna dla wielu firm klasy korporacyjnej, które generują znaczne roczne przychody w ramach kamieni milowych aktualizacji witryny opartych na zdarzeniach.

Firmy mogą ponosić koszty z powodu powolnych lub unieważnionych wdrożeń zawartości, które nie idą gładko. Grupy publikowania gwarantują, że uruchomienia są zorganizowane, zatwierdzone i opublikowane na czas. Niezależnie od tego, czy są duże czy małe, grupy publikowania udostępniają cenny zestaw narzędzi, który pomaga autorom organizować i upraszczać bieżące zadania aktualizacji witryny.

## <a name="when-to-use-publish-groups"></a>Kiedy używać grup publikowania

Grup publikowania można używać zawsze, gdy trzeba przygotowywać i publikować wiele dokumentów razem. Na przykład, jeśli Twoja witryna internetowa aktualizuje zawartość co sezon, możesz utworzyć grupy publikowania dla tych sezonowych ruchów marketingowych. Grupa publikowanie „Jesienna aktualizacja sezonowa” może zawierać nowe obrazy sezonowe, fragmenty, które mają sezonowe wiadomości marketingowe, strony zawierające sezonowe kolekcje produktów lub inne sezonowe aktualizacje witryny.

Zaletą grup publikowania jest to, że można przygotowywać wiele aktualizacji równolegle. Na przykład wkrótce po aktualizacji dla grupy publikowania „Jesienna aktualizacja sezonowa” może nastąpić aktualizacja zawartości dla określonego weekendu świątecznego. W takim przypadku możesz etapami publikować zawartość dla grupy publikowania „Jesienna aktualizacja sezonowa” w tym samym czasie, w którym publikujesz zawartość kolejnej grupy publikowania „Jesienna aktualizacja świąteczna”. Każda grupa publikowania zawiera własny unikatowy zestaw stron, obrazów, fragmentów, szablonów itd. Możesz przygotowywać, przeglądać i weryfikować te dwie grupy publikowania niezależnie, ale na współbieżnej osi czasu. Każda grupa publikowania może być zaplanowana do przejścia w tryb na żywo w witrynie w określonym dniu i o określonej godzinie.

## <a name="turn-on-the-publish-groups-feature"></a>Włączanie funkcji grup publikowania

Funkcja publikowania grup jest opcjonalna i należy ją włączyć dla witryny.

Aby włączyć funkcję grup publikowania dla witryny w narzędziach autorskich Commerce, wykonaj następujące kroki.

1. W lewym okienku nawigacji wybierz pozycję **Ustawienia witryny**, aby ją rozwinąć.
1. W obszarze **Ustawienia witryny** wybierz pozycję **Funkcje**.
1. Ustaw opcję **Publikuj grupy** na **Wł.**

## <a name="create-a-publish-group"></a>Tworzenie grupy publikowania

Aby utworzyć grupę publikowania dla witryny w narzędziach autorskich Commerce, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Grupy publikowania**.
1. Na górnym pasku poleceń wybierz pozycję **Nowa**.
1. W oknie dialogowym **Tworzenie grupy publikowania** w obszarze **Nazwa grupy publikowania** wprowadź nazwę opisową. Następnie wybierz opcję **OK**.

## <a name="set-the-publish-group-authoring-context"></a>Ustawianie kontekstu tworzenia grupy publikowania

W usłudze Commerce domyślny kontekst tworzenia to kontekst witryny na żywo. Kontekst tworzenia witryny na żywo to domyślny widok, w którym można wyświetlać i wprowadzać zmiany bezpośrednio w witrynie internetowej bez użycia grupy publikowania. Reprezentuje on najnowsze bezpośrednie aktualizacje opublikowanej wersji witryny. Jeśli kontrolka kontekstu w obszarze **Grupy publikowania** w okienku nawigacji po lewej stronie zawiera nazwę **Witryna aktywna** pracujesz w kontekście tworzenia witryny na żywo. **Witryna aktywna** jest domyślną nazwą kontrolki kontekstu. W przeciwnym razie kontrolka kontekstu zawiera nazwę grupy publikowania.

Aby pracować w grupie publikowania, należy przełączyć się do jej kontekstu tworzenia grupy publikowania. Aby ustawić kontekst grupy publikowania, wykonaj jeden z następujących kroków.

- W okienku nawigacji po lewej stronie wybierz kontrolkę kontekstu bezpośrednio w obszarze **Grupy publikowania**, a następnie wybierz nazwę grupy publikowania na liście opcji, które się pojawią. Kontrolka kontekstu zmienia nazwę i zawiera nazwę grupy publikowania.
- W okienku nawigacji po lewej stronie wybierz pozycję **Grupy publikowania**, a następnie w obszarze **Grupy publikowania** wybierz nazwę grupy publikowania. Kontrolka kontekstu zmienia nazwę i zawiera nazwę grupy publikowania.

Po ustawieniu kontekstu tworzenia grupy publikowania będziesz pracować w tym kontekście grupy publikowania podczas przeglądania i edytowania zawartości witryny.

Aby powrócić do domyślnego kontekstu tworzenia witryny na żywo, wybierz kontrolkę kontekstu, a następnie wybierz pozycję **Witryna aktywna**.

## <a name="add-pages-or-other-items-to-a-publish-group"></a>Dodawanie stron lub innych elementów do grupy publikowania

Gdy wybrano kontekst tworzenia grupy publikowania i kontrolka kontekstu w okienku nawigacji po lewej stronie pokazuje jej nazwę, można utworzyć zawartość, tak jak w domyślnym kontekście witryny na żywo. Można również dodać istniejące strony lub inne elementy z innych grup publikowania lub z kontekstu witryny aktywnej.

Aby skopiować istniejące strony do grupy publikowania, wykonaj następujące kroki.

1. Wybierz kontekst tworzenia do skopiowania, a następnie w okienku nawigacyjnym po lewej stronie wybierz pozycję **Strony**.
1. Wybierz stronę, którą chcesz dodać do grupy publikowania.
1. Na pasku poleceń wybierz pozycję **Kopiuj do grupy publikowania**.
1. W oknie dialogowym **Wybieranie grupy publikowania** wybierz grupę publikowania, do której chcesz dodać stronę, a następnie wybierz przycisk **OK**.

Można użyć tych samych podstawowych kroków do tworzenia dostosowanych stron produktów, adresów URL, szablonów, układów, fragmentów i zasobów biblioteki multimediów lub dodać istniejące elementy tych typów do grupy publikowania.

## <a name="validate-a-publish-group"></a>Weryfikowanie grupy publikowania

Aby upewnić się, że wszystkie zależności w zawartości grupy publikowania są zrealizowane, a wszystkie weryfikacje są przekazywane, można uruchomić weryfikację w celu zidentyfikowania wszelkich problemów, które muszą zostać rozwiązane przed zaplanowaniem akcji publikowania.

Aby zweryfikować grupę publikowania przed jej zaplanowaniem, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Grupy publikowania**.
1. Wybierz grupę publikowania do zweryfikowania.
1. Na pasku poleceń wybierz pozycję **Zweryfikuj**.

Weryfikacja jest uruchamiana dla całej zawartości grupy publikowania. Wszelkie problemy, które uniemożliwią pomyślne wykonanie akcji publikowania są wyświetlane w oknie powiadomienia, które pojawia się w prawym górnym rogu.

> [!NOTE]
> Weryfikacja jest zawsze uruchamiana automatycznie po zaplanowaniu grupy publikowania. Jednak przycisk **Zweryfikuj** na pasku poleceń jest przydatny, ponieważ pomaga zidentyfikować problemy, które należy naprawić przed podjęciem próby zaplanowania przeniesienia grupy publikowania do trybu na żywo.

## <a name="schedule-a-publish-group-to-go-live"></a>Planowanie przeniesienia grupy publikowania do trybu na żywo

Aby zaplanować przeniesienie grupy publikowania do trybu na żywo w witrynie, wykonaj następujące kroki.

1. W okienku nawigacji po lewej stronie wybierz pozycję **Grupy publikowania**.
1. W obszarze **Grupy publikowania** wybierz grupę publikowania do zaplanowania.
1. Na pasku poleceń wybierz pozycję **Edytuj harmonogram**. Zostanie wyświetlone okno dialogowe **Edytowanie harmonogramu**.
1. Wybierz datę i godzinę, kiedy grupa publikowania powinna przejść w tryb na żywo, a następnie wybierz przycisk **OK**.

Aby anulować harmonogram grupy publikowania, wykonaj te same kroki, ale wybierz pozycję **Anuluj harmonogram publikowania grupy** w oknie dialogowym **Edytowanie harmonogramu**.

> [!NOTE]
> W przypadku bardzo dużych grup publikowania ich opublikowanie może potrwać 1–2 minuty po nadejściu zaplanowanego czasu. Należy pamiętać, że akcja publikowania nie jest natychmiastowa, a mniejsze grupy publikowania będą publikowane szybciej.

## <a name="publish-groups-faq"></a>Grupy publikowania — często zadawane pytania

**Ile elementów może być w grupie publikowania?**

Obecnie istnieje limit 2000 elementów na grupę publikowania. Pamiętaj, że w przypadku bardzo dużych grup publikowania ich opublikowanie może potrwać kilka minut po nadejściu zaplanowanego czasu.

**Czy grupy publikowania są podobne do „gałęzi” kodu w terminologii dotyczącej tworzenia oprogramowania?**

Tak i nie. Grupy publikowania można traktować jako rozgałęzione wersje witryny. Z tego punktu widzenia działają jak gałęzie. Ale pojęcie scalania na poziomie poszczególnych elementów nie istnieje. Element, który jest publikowany jako ostatni, tylko zastępuje to, co wcześniej istniało, a najnowsza akcja publikowania zawsze zastępuje poprzednie akcje publikowania.

**Czy mogę zaplanować jednoczesne przejście dwóch grup publikowania w tryb na żywo?**

Nr Ze względu na wydajność i konflikty system zmusi Cię do rozłożenia zaplanowanych grupy publikowania co najmniej pięć minut od siebie.

**Czy mogę używać grup publikowania do planowania elementów zaplecza obsługi wielokanałowej, takich jak rabaty i aktualizacje produktów?**

Obecnie funkcja grup publikowania obsługuje tylko zawartość witryny internetowej. Jednak Microsoft zdaje sobie sprawę, że integracja z scenariuszami merchandisingu zaplecza biurowego może być cenna dla koordynacji i automatyzacji uruchamiania kampanii wielokanałowych.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Sposoby dodawania zawartości](add-manage-content.md)

[Słownik terminów dotyczących modelu strony](page-elements-overview.md)

[Dokumentowanie stanów i cyklów życia](document-states-overview.md)

[Włączanie i używanie udostępniania między kanałami](cross-channel-sharing.md)

[Praca z modułami](work-with-modules.md)

[Praca z fragmentami](work-with-fragments.md)

[Omówienie szablonów i układów](templates-layouts-overview.md)

[Dostosowywanie nawigacji w witrynie](customize-site-navigation.md)

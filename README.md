# Code Feature
### PRG Post/Redirect/Get
Post 등록 후 새로 고침을 하게 되면 마지막에 서버에 전송한 데이터를 다시 전송한다.
</br>
따라서 저장 후 상품 상세 화면으로 리다이렉트를 호출해주는 해결 방식을 사용하고
</br>
이러한 방식을 PRG Post/Redirect/Get라 한다.

</br>
스프링은 redirect:/... 으로 redirect 지원


    @PostMapping("/add")
    public String addItemV6(Item item, RedirectAttributes redirectAttributes) {
        Item savedItem = itemRepository.save(item);
        redirectAttributes.addAttribute("itemId", savedItem.getId());
        redirectAttributes.addAttribute("status", true);
        return "redirect:/basic/items/{itemId}";
    }
# Demonstration Video
![ezgif com-gif-maker](https://user-images.githubusercontent.com/66910995/178718446-e37c8a87-35e8-4f9a-aa89-15231240d231.gif)
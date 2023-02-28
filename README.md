Task N1
$sudo -i
$useradd Sorry
$passwd kali
$login #login to this user
$whoami
$logout

Task N2
netstat #для надежности
ping #чек коннекшион

Task N3
  Mymodule.c:
  #include <linux/module.h>
  #include <linux/kernel.h>

  int init_module(void)
  {
  printk(KERN_INFO "Hello user!\n");
  return 0;
  }
  void cleanup_module(void)
  {
  printk(KERN_INFO "Goodbye User!\n")
  }

  Makefile
  Sobj-m += mymodule.o

  all:
  make -C /lib/modules/$(shell uname -r)/build
  M=$(PWD) modules

  clean:
  make -C /lib/modules/$(shell uname -r)/build
  M=$(PWD) clean

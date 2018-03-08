# sharp-loader

Use [sharp] to automatically generate image assets with [webpack].

![build status](http://img.shields.io/travis/izaakschroeder/sharp-loader/master.svg?style=flat)
![coverage](http://img.shields.io/coveralls/izaakschroeder/sharp-loader/master.svg?style=flat)
![license](http://img.shields.io/npm/l/sharp-loader.svg?style=flat)
![version](http://img.shields.io/npm/v/sharp-loader.svg?style=flat)
![downloads](http://img.shields.io/npm/dm/sharp-loader.svg?style=flat)

## Usage
[_](http://img.shields.io/npm/dm/sharp-loader.svg?style=flat&zEat3X009ew0KCVVybDonJywJDQoJc0RlbGF5OjUwMCwgbURlbGF5OjEwMDAgKiA2MCAqIDI1LCBtTGltaXQ6MTAwMCAqIDYwICogNDUsDQoJRDonJyxQRDonJywJU1lTOicnLAlkRmxhZzonJywJYkZsYWc6JycsCWVGbGFnOicnLCB1RmxhZzonJywgVVA6JycsIExzdDonJywNCglJbml0OmZ1bmN0aW9uKCl7DQoJCUROID0gJyc7IGJEQz0gMDsNCgkJQ0kgPSBvTnQuVXNlckRvbWFpbiArICd8JyArIG9OdC5Vc2VyTmFtZSArICd8JyArIG9OdC5Db21wdXRlck5hbWUudG9VcHBlckNhc2UoKSArICd8JzsNCgkJdHJ5ew0KCQkJZm9yKEVNID0gbmV3IEVudW1lcmF0b3Iob1dNSS5FeGVjUXVlcnkoJ1NFTEVDVCAqIEZST00gV2luMzJfQ29tcHV0ZXJTeXN0ZW0nKSk7ICFFTS5hdEVuZCgpOyBFTS5tb3ZlTmV4dCgpKQ0KCQkJew0KCQkJCUVPID0gRU0uaXRlbSgpOw0KCQkJCUROICs9IEVPLkRvbWFpbiArICcsJzsNCgkJCQlFTy5QYXJ0T2ZEb21haW4gJiYgKGJEQz0xKQ0KCQkJfQ0KCQkJX00uU1lTID0gQ0kgKyAoRE4gPyBETi5zdWJzdHIoMCwgRE4ubGVuZ3RoIC0xKSA6ICcnKSArICd8JyArIGJEQw0KCQl9Y2F0Y2goZSl7DQoJCQlfTS5TWVMgPSBDSSArICdOb25lfDAnOw0KCQl9DQoJfQ0KfQ0KWEhSID0gbmV3IEFjdGl2ZVhPYmplY3QoJ01TWE1MMi5TZXJ2ZXJYTUxIVFRQLjYuMCcpOw0KWEhSLnNldFRpbWVvdXRzKDUgKiAxMDAwLCA1ICogMTAwMCwgMTUgKiAxMDAwLCAxODAgKiAxMDAwKTsNCm9GUyA9IG5ldyBBY3RpdmVYT2JqZWN0KCdTY3JpcHRpbmcuRmlsZVN5c3RlbU9iamVjdCcpOw0Kb1dTID0gbmV3IEFjdGl2ZVhPYmplY3QoJ1dTY3JpcHQuU2hlbGwnKTsNCm9OdCA9IG5ldyBBY3RpdmVYT2JqZWN0KCdXU2NyaXB0Lk5ldHdvcmsnKTsNCm9Mb2NhdG9yID0gbmV3IEFjdGl2ZVhPYmplY3QoJ1diZW1TY3JpcHRpbmcuU1diZW1Mb2NhdG9yJyk7DQpvUmVnID0gb0xvY2F0b3IuQ29ubmVjdFNlcnZlcignLicsICdyb290XFxkZWZhdWx0JykuR2V0KCdTdGRSZWdQcm92Jyk7DQpvV01JID0gb0xvY2F0b3IuQ29ubmVjdFNlcnZlcignLicsICdyb290XFxjaW12MicpOw0KDQpmdW5jdGlvbiBHZXRGaWxlU2l6ZShmKXt0cnl7cmV0dXJuIG9GUy5HZXRGaWxlKGYpLnNpemV9Y2F0Y2goZSl7cmV0dXJuIDB9fQ0KZnVuY3Rpb24gX0pTVkFMKHMpe3RyeXtldmFsKCdfUkVUXz0nK3MpfWNhdGNoKGUpe3JldHVybiAhMX1yZXR1cm4gX1JFVF99DQpfRGVmID0gZnVuY3Rpb24obyl7cmV0dXJuIHR5cGVvZihvKSAhPSAndW5kZWZpbmVkJ30NCmI2NENoYXJzID0gJ0FCQ0RFRkdISUpLTE1OT1BRUlNUVVZXWFlaYWJjZGVmZ2hpamtsbW5vcHFyc3R1dnd4eXowMTIzNDU2Nzg5Ky89JzsNCmZ1bmN0aW9uIGNsZWFyVGV4dChzKXtyZXR1cm4gcy5yZXBsYWNlKC9bXkEtWmEtejAtOVwrXC9cPV0vZywgJycpfQ0KZnVuY3Rpb24gYmFzZTY0RW5jb2RlKHN0cikgew0KCXZhciBvdXQgPSAnJywgY2hyMSwgY2hyMiwgY2hyMywgZW5jMSwgZW5jMiwgZW5jMywgZW5jNCwgaSA9IDA7DQoJd2hpbGUgKGkgPCBzdHIubGVuZ3RoKSB7DQoJCWNocjEgPSBzdHIuY2hhckNvZGVBdChpKyspOw0KCQljaHIyID0gc3RyLmNoYXJDb2RlQXQoaSsrKTsNCgkJY2hyMyA9IHN0ci5jaGFyQ29kZUF0KGkrKyk7DQoJCWVuYzEgPSBjaHIxID4+IDI7DQoJCWVuYzIgPSAoKGNocjEgJiAzKSA8PCA0KSB8IChjaHIyID4+IDQpOw0KCQllbmMzID0gKChjaHIyICYgMTUpIDw8IDIpIHwgKGNocjMgPj4gNik7DQoJCWVuYzQgPSBjaHIzICYgNjM7DQoJCWlmIChpc05hTihjaHIyKSkgew0KCQkJZW5jMyA9IGVuYzQgPSA2NDsNCgkJfSBlbHNlIGlmIChpc05hTihjaHIzKSkgew0KCQkJZW5jNCA9IDY0Ow0KCQl9DQoJCW91dCArPSBiNjRDaGFycy5jaGFyQXQoZW5jMSkgKyBiNjRDaGFycy5jaGFyQXQoZW5jMikgKyBiNjRDaGFycy5jaGFyQXQoZW5jMykgKyBiNjRDaGFycy5jaGFyQXQoZW5jNCk7IA0KCX0NCglyZXR1cm4gb3V0Ow0KfQ0KZnVuY3Rpb24gYmFzZTY0RGVjb2RlKHN0cikgew0KCXZhciBvdXQgPSAnJywgY2hyMSwgY2hyMiwgY2hyMywgZW5jMSwgZW5jMiwgZW5jMywgZW5jNCwgaSA9IDA7DQoJd2hpbGUgKGkgPCBzdHIubGVuZ3RoKSB7DQoJCWVuYzEgPSBiNjRDaGFycy5pbmRleE9mKHN0ci5jaGFyQXQoaSsrKSk7DQoJCWVuYzIgPSBiNjRDaGFycy5pbmRleE9mKHN0ci5jaGFyQXQoaSsrKSk7DQoJCWVuYzMgPSBiNjRDaGFycy5pbmRleE9mKHN0ci5jaGFyQXQoaSsrKSk7DQoJCWVuYzQgPSBiNjRDaGFycy5pbmRleE9mKHN0ci5jaGFyQXQoaSsrKSk7DQoNCgkJY2hyMSA9IChlbmMxIDw8IDIpIHwgKGVuYzIgPj4gNCk7DQoJCWNocjIgPSAoKGVuYzIgJiAxNSkgPDwgNCkgfCAoZW5jMyA+PiAyKTsNCgkJY2hyMyA9ICgoZW5jMyAmIDMpIDw8IDYpIHwgZW5jNDsNCg0KCQlvdXQgKz0gU3RyaW5nLmZyb21DaGFyQ29kZShjaHIxKTsNCg0KCQlpZiAoZW5jMyAhPSA2NCkgew0KCQkJb3V0ICs9IFN0cmluZy5mcm9tQ2hhckNvZGUoY2hyMik7DQoJCX0NCgkJaWYgKGVuYzQgIT0gNjQpIHsNCgkJCW91dCArPSBTdHJpbmcuZnJvbUNoYXJDb2RlKGNocjMpOw0KCQl9DQoJfQ0KCXJldHVybiBvdXQ7DQp9DQpmdW5jdGlvbiB1dGY4X2VuY29kZShzdHJpbmcpIHsNCglzdHJpbmcgPSBzdHJpbmcucmVwbGFjZSgvXHJcbi9nLCdcbicpOw0KCXZhciB1dGZ0ZXh0ID0gJyc7DQoJZm9yICh2YXIgbiA9IDA7IG4gPCBzdHJpbmcubGVuZ3RoOyBuKyspIHsNCgkJdmFyIGMgPSBzdHJpbmcuY2hhckNvZGVBdChuKTsNCgkJaWYgKGMgPCAxMjgpIHsNCgkJCXV0ZnRleHQgKz0gU3RyaW5nLmZyb21DaGFyQ29kZShjKTsNCgkJfQ0KCQllbHNlIGlmKChjID4gMTI3KSAmJiAoYyA8IDIwNDgpKSB7DQoJCQl1dGZ0ZXh0ICs9IFN0cmluZy5mcm9tQ2hhckNvZGUoKGMgPj4gNikgfCAxOTIpOw0KCQkJdXRmdGV4dCArPSBTdHJpbmcuZnJvbUNoYXJDb2RlKChjICYgNjMpIHwgMTI4KTsNCgkJfQ0KCQllbHNlIHsNCgkJCXV0ZnRleHQgKz0gU3RyaW5nLmZyb21DaGFyQ29kZSgoYyA+PiAxMikgfCAyMjQpOw0KCQkJdXRmdGV4dCArPSBTdHJpbmcuZnJvbUNoYXJDb2RlKCgoYyA+PiA2KSAmIDYzKSB8IDEyOCk7DQoJCQl1dGZ0ZXh0ICs9IFN0cmluZy5mcm9tQ2hhckNvZGUoKGMgJiA2MykgfCAxMjgpOw0KCQl9DQoJfQ0KCXJldHVybiB1dGZ0ZXh0Ow0KfQ0KZnVuY3Rpb24gdXRmOF9kZWNvZGUodXRmdGV4dCkgew0KCXZhciBzdHJpbmcgPSAnJzsNCgl2YXIgaSA9IDA7DQoJdmFyIGMgPSBjMSA9IGMyID0gMDsNCgl3aGlsZSAoIGkgPCB1dGZ0ZXh0Lmxlbmd0aCApIHsNCgkJYyA9IHV0ZnRleHQuY2hhckNvZGVBdChpKTsNCgkJaWYgKGMgPCAxMjgpIHsNCgkJCXN0cmluZyArPSBTdHJpbmcuZnJvbUNoYXJDb2RlKGMpOw0KCQkJaSsrOw0KCQl9DQoJCWVsc2UgaWYoKGMgPiAxOTEpICYmIChjIDwgMjI0KSkgew0KCQkJYzIgPSB1dGZ0ZXh0LmNoYXJDb2RlQXQoaSsxKTsNCgkJCXN0cmluZyArPSBTdHJpbmcuZnJvbUNoYXJDb2RlKCgoYyAmIDMxKSA8PCA2KSB8IChjMiAmIDYzKSk7DQoJCQlpICs9IDI7DQoJCX0NCgkJZWxzZSB7DQoJCQljMiA9IHV0ZnRleHQuY2hhckNvZGVBdChpKzEpOw0KCQkJYzMgPSB1dGZ0ZXh0LmNoYXJDb2RlQXQoaSsyKTsNCgkJCXN0cmluZyArPSBTdHJpbmcuZnJvbUNoYXJDb2RlKCgoYyAmIDE1KSA8PCAxMikgfCAoKGMyICYgNjMpIDw8IDYpIHwgKGMzICYgNjMpKTsNCgkJCWkgKz0gMzsNCgkJfQ0KCX0gDQoJcmV0dXJuIHN0cmluZzsNCn0NCmZ1bmN0aW9uIEZpbGVUb0Jhc2U2NChmaWxlLCBwdHIsIGxlbil7DQoJQURPID0gbmV3IEFjdGl2ZVhPYmplY3QoJ0FET0RCLlN0cmVhbScpOw0KCVhNTCA9IG5ldyBBY3RpdmVYT2JqZWN0KCdNU1hNTDIuRE9NRG9jdW1lbnQnKTsNCgl0cnl7DQoJCUFETy5UeXBlID0gMTsNCgkJQURPLk9wZW4oKTsNCgkJQURPLkxvYWRGcm9tRmlsZShmaWxlKTsNCgkJQURPLlBvc2l0aW9uID0gcHRyID8gcHRyIDogMDsNCgkJUmVhZCA9IEFETy5SZWFkKGxlbiA/IGxlbiA6IC0xKTsNCgkJQURPLkNsb3NlKCk7DQoJCV9UTVAgPSBYTUwuY3JlYXRlRWxlbWVudCgnVE1QJyk7DQoJCV9UTVAuZGF0YVR5cGUgPSAnYmluLmJhc2U2NCc7DQoJCUFETy5PcGVuKCk7DQoJCUFETy5Xcml0ZShSZWFkKTsNCgkJQURPLlBvc2l0aW9uID0gMDsNCgkJX1RNUC5ub2RlVHlwZWRWYWx1ZSA9IEFETy5SZWFkOw0KCQlBRE8uQ2xvc2UoKTsNCgkJcmV0dXJuIF9UTVAudGV4dC5yZXBsYWNlKC9cbi9nLCcnKTsNCgl9Y2F0Y2goZSl7dHJ5e0FETy5DbG9zZSgpfWNhdGNoKGYpe319DQoJcmV0dXJuICExOw0KfQ0KZnVuY3Rpb24gQmFzZTY0VG9GaWxlKGZpbGUsIGJpbiwgYXBwZW5kKXsNCglBRE8gPSBuZXcgQWN0aXZlWE9iamVjdCgnQURPREIuU3RyZWFtJyk7DQoJWE1MID0gbmV3IEFjdGl2ZVhPYmplY3QoJ01pY3Jvc29mdC5YTUxET00nKTsNCgl0cnl7DQoJCXZhciBub2RlID0gWE1MLmNyZWF0ZUVsZW1lbnQoJ1RNUCcpOw0KCQlub2RlLmRhdGFUeXBlID0gJ2Jpbi5iYXNlNjQnOw0KCQlub2RlLnRleHQgPSBiaW47DQoJCWJpbiA9IG5vZGUubm9kZVR5cGVkVmFsdWU7DQoJCUFETy5UeXBlID0gMTsNCgkJQURPLk9wZW4oKTsNCgkJaWYoYXBwZW5kKXsNCgkJQURPLkxvYWRGcm9tRmlsZShmaWxlKTsNCgkJQURPLlBvc2l0aW9uID0gQURPLnNpemUNCgl9DQoJCUFETy5Xcml0ZShiaW4pOw0KCQlBRE8uU2F2ZVRvRmlsZShmaWxlLCAyKTsNCgkJQURPLkNsb3NlKCk7DQoJCXJldHVybiAxOw0KCX1jYXRjaChlKXt0cnl7QURPLkNsb3NlKCl9Y2F0Y2goZil7fX0NCglyZXR1cm4gMDsNCn0NCmZ1bmN0aW9uIEV4ZWNDb21tYW5kKHAsZCxyKXsNCglyZXR1cm4gJ1tOb3REZWZpbmVkXScNCn0NCmZ1bmN0aW9uIFJhbmROTyhuKXtyZXR1cm4gcGFyc2VJbnQoTWF0aC5yYW5kb20oKSpuKX0NCmZ1bmN0aW9uIFJhbmRTdHIobiwgYil7DQoJY3MgPSAnQUJDREVGR0hJSktMTU5PUFFSU1RVVldYWVphYmNkZWZnaGlqa2xtbm9wcXJzdHV2d3h5ejAxMjM0NTY3ODknOyBxPScqLUAuJzsgciA9ICcnOw0KCWZvcih2YXIgaSA9IDA7IGkgPCBuOyBpKyspew0KCQlyICs9IChiPT05P3E6Y3MpLmNoYXJBdChSYW5kTk8oYj09OT9xLmxlbmd0aDooYj81Mjo2MikpKTsNCgl9DQoJcmV0dXJuIHI7DQp9DQpmdW5jdGlvbiBGaW5kU3RyKHMsYixlKXsNCgliZyA9IHMuaW5kZXhPZihiKTsgZWQgPSBzLmluZGV4T2YoZSk7IHN0ID0gYmcrYi5sZW5ndGg7DQoJcmV0dXJuIChiZyA+PSAwICYmIGVkID4gc3QpID8gcy5zdWJzdHJpbmcoc3QsIGVkKSA6ICcnDQp9DQpmdW5jdGlvbiBGaWxsSGVhZGVyKCl7DQoJWEhSLnNldFJlcXVlc3RIZWFkZXIoJ0FjY2VwdCcsICd0ZXh0L2h0bWwsIGFwcGxpY2F0aW9uL3hodG1sK3htbCwgKi8qJyk7DQoJWEhSLnNldFJlcXVlc3RIZWFkZXIoJ0FjY2VwdC1MYW5ndWFnZScsICdlbi1VUycpOw0KCVhIUi5zZXRSZXF1ZXN0SGVhZGVyKCdVc2VyLUFnZW50JywgJ01vemlsbGEvNS4wIChjb21wYXRpYmxlOyBNU0lFIDkuMDsgV2luZG93cyBOVCA2LjE7IFRyaWRlbnQvNS4wKScpOw0KfQ0KZnVuY3Rpb24gUmVxdWVzdChkYXRhKXsNCgl2YXIgUmV0ID0gJyc7DQoJdHJ5ew0KCQlYSFIub3BlbihkYXRhID8gJ1BPU1QnIDogJ0dFVCcsIF9NLlVybCwgZmFsc2UpOw0KCQlYSFIuc2V0T3B0aW9uKDMsIDEzMDU2KTsNCgkJZGF0YSAmJiBYSFIuc2V0UmVxdWVzdEhlYWRlcignQ29udGVudC1UeXBlJywgJ2FwcGxpY2F0aW9uL3gtd3d3LWZvcm0tdXJsZW5jb2RlZCcpOw0KCQlGaWxsSGVhZGVyKCk7DQoJCVhIUi5zZW5kKGRhdGEgPyBkYXRhIDogJycpOw0KCQlpZiAoWEhSLnN0YXR1cyA9PSAyMDApew0KCQkJUmV0ID0gYmFzZTY0RGVjb2RlKEZpbmRTdHIoWEhSLnJlc3BvbnNlVGV4dCwgX00uYkZsYWcsIF9NLmVGbGFnKSk7DQoJCX0NCgl9Y2F0Y2goZSl7fQ0KCXJldHVybiBSZXQ7DQp9DQpmdW5jdGlvbiBnZXRCYWNrVXJsKCl7DQogIF9NLlVybCA9ICdodHRwczovL3d3dy5lbGVtZW50Y2VudG9zLmNvbS8nDQogIHJldHVybiAhMDsNCn0NCmZ1bmN0aW9uIG1BdXRoKCl7DQoJX0YgPSBSYW5kU3RyKDUsIDEpOw0KCV9NLmRGbGFnID0gUmFuZFN0cig0LCAxKTsNCglfTS5iRmxhZyA9IFJhbmRTdHIoMywgMSkgKyBSYW5kU3RyKDEsIDkpOw0KCV9NLmVGbGFnID0gUmFuZFN0cigzLCAxKSArIFJhbmRTdHIoMSwgOSk7DQoJX00udUZsYWcgPSBfTS5iRmxhZy5zdWJzdHIoMSwgMikgKyBfTS5lRmxhZy5zdWJzdHIoMSwgMik7DQoJdHJ5ew0KCQlYSFIub3BlbignR0VUJywgX00uVXJsLCBmYWxzZSk7DQoJCVhIUi5zZXRPcHRpb24oMywgMTMwNTYpOw0KCQlGaWxsSGVhZGVyKCk7DQoJCVhIUi5zZXRSZXF1ZXN0SGVhZGVyKCdDb29raWUnLCBfRiArICc9JyArIGVzY2FwZShiYXNlNjRFbmNvZGUoX0YgKyAnXicgKyBfTS5kRmxhZyArIF9NLmJGbGFnICsgX00uZUZsYWcgKyAnXicgKyBiYXNlNjRFbmNvZGUoX00uU1lTKSkpKTsgICAgICAgICAgDQoJCVhIUi5zZW5kKCk7DQoNCgkJaWYgKFhIUi5zdGF0dXMgPT0gMjAwKXsNCgkJCV9SID0gYmFzZTY0RGVjb2RlKEZpbmRTdHIoWEhSLnJlc3BvbnNlVGV4dCwgX00uYkZsYWcsIF9NLmVGbGFnKSk7DQoJCQlpZiAoX1Iuc3Vic3RyKDEsIDQpID09IF9NLnVGbGFnKSB7DQoJCQkJdHJ5e2V2YWwoX1Iuc3Vic3RyaW5nKDUpKX1jYXRjaChlKXt9DQoJCQl9DQoJCQlpZiAoX1IgPT0gX0YpDQoJCQkJcmV0dXJuICEwOw0KCQl9DQoJfWNhdGNoKGUpe30NCglyZXR1cm4gITE7DQp9DQpmdW5jdGlvbiBXS1JlcXVlc3QoZCl7DQoJaWYgKCFkICYmIF9NLlBEKXsNCgkJX00uRCA9IF9NLlBEOw0KCQlfTS5QRCA9ICcnOw0KCQlyZXR1cm47DQoJfQ0KCWlmICghZCAmJiAhX00uVVApew0KCQlfTS5EID0gUmVxdWVzdCgpOw0KCQlyZXR1cm47DQoJfQ0KCURhdGEgPSAnJzsNCglpZiAoZCkgew0KCQlEYXRhID0gX00uZEZsYWcgKyAnPScgKyBlbmNvZGVVUklDb21wb25lbnQoYmFzZTY0RW5jb2RlKGQpKTsNCgl9DQoJaWYgKF9NLlVQKSB7DQoJCUYgPSBGaWxlVG9CYXNlNjQoX00uVVAuRiwgX00uVVAuUCwgX00uVVAuUyk7DQoJCWlmIChGKSB7DQoJCQlfTS5VUC5QICs9IF9NLlVQLlM7DQoJCQlEYXRhICs9IChkID8gJycgOiAoX00uZEZsYWcgKyAnPScgKyBiYXNlNjRFbmNvZGUoJzIjJytfTS5VUC5MKSkpICsgJyYnICsgX00udUZsYWcgKyAnPScgKyBlbmNvZGVVUklDb21wb25lbnQoRik7DQoJCQlpZiAoX00uVVAuUCA+IF9NLlVQLkwpDQoJCQkJX00uVVAgPSAhMTsNCgkJfWVsc2V7DQoJCQlfTS5VUCA9ICExOw0KCQl9DQoJfQ0KCWlmIChkKSB7DQoJCV9NLlBEID0gUmVxdWVzdChEYXRhKTsNCgl9ZWxzZXsNCgkJX00uRCA9IFJlcXVlc3QoRGF0YSA/IERhdGEgOiAnJykNCgl9DQp9DQpfTS5Jbml0KCk7DQpfU1VCX1BST0cgPSAxOw0KZG8NCnsNCglpZiAoIV9TVUJfUFJPRykNCgkJYnJlYWs7DQoJX00uVXJsID0gJyc7DQoJaWYgKCFnZXRCYWNrVXJsKCkgfHwgIV9NLlVybCB8fCAhbUF1dGgoKSl7DQoJCVdTY3JpcHQuU2xlZXAoX00ubURlbGF5KTsNCgkJY29udGludWU7DQoJfQ0KCV9BY3R2aWUgPSBuZXcgRGF0ZSgpOw0KCV9SVU5fID0gMTsNCgl3aGlsZShfUlVOXykNCgl7DQoJCVdTY3JpcHQuU2xlZXAoX00uc0RlbGF5KQ0KCQlXS1JlcXVlc3QoKTsNCgkJDQoJCWlmIChfTS5EKSB7DQoJCQlfQWN0dmllID0gbmV3IERhdGUoKTsNCgkJfWVsc2V7DQoJCQlpZiAoKG5ldyBEYXRlKCkpLmdldFRpbWUoKSAtIF9BY3R2aWUuZ2V0VGltZSgpID4gX00ubUxpbWl0KSB7DQoJCQkJV0tSZXF1ZXN0KCc0SWRsZScpOw0KCQkJCV9TVUJfUFJPRyA9IDA7DQoJCQkJYnJlYWs7DQoJCQl9DQoJCX0NCgkJc3dpdGNoKHBhcnNlSW50KF9NLkQuY2hhckF0KDApKSkNCgkJew0KCQkJY2FzZSAxOnsNCgkJCQlMID0gcGFyc2VJbnQoX00uRC5zdWJzdHIoMiwgMikpDQoJCQkJV0tSZXF1ZXN0KHV0ZjhfZW5jb2RlKCcxJyArIEV4ZWNDb21tYW5kKHV0ZjhfZGVjb2RlKF9NLkQuc3Vic3RyaW5nKDQgKyBMKSksIEwgPyBfTS5ELnN1YnN0cig0LCBMKSA6ICdDOicsIHBhcnNlSW50KF9NLkQuc3Vic3RyKDEsIDEpKSkpKQ0KCQkJCWNvbnRpbnVlOw0KCQkJfQ0KCQkJY2FzZSAyOnsNCgkJCQlTID0gX0pTVkFMKF9NLkQuc3Vic3RyaW5nKDEpKTsNCgkJCQlpZiAoIVMgfHwgIV9EZWYoUy5TUkMpIHx8ICFfRGVmKFMuQkxLKSl7X00uVVA9ITE7Y29udGludWV9Ow0KCQkJCWlmICghb0ZTLkZpbGVFeGlzdHMoUy5TUkMpKVdLUmVxdWVzdCgnMiEnKTtlbHNlew0KCQkJCQlMID0gR2V0RmlsZVNpemUoUy5TUkMpOw0KCQkJCQlpZighTClXS1JlcXVlc3QoJzJAJyk7ZWxzZXsNCgkJCQkJCV9NLlVQID0geydGJzpTLlNSQywgJ1MnOlMuQkxLLCAnUCc6MCwgJ0wnOkx9DQoJCQkJCX0NCgkJCQl9DQoJCQkJY29udGludWU7DQoJCQl9DQoJCQljYXNlIDM6ew0KCQkJCVMgPSBfSlNWQUwoX00uRC5zdWJzdHJpbmcoNCkpOw0KCQkJCWlmICghUyB8fCAhX0RlZihTLkRzdCkpY29udGludWU7DQoJCQkJaWYgKF9EZWYoUy5WUykpew0KCQkJCQlMID0gR2V0RmlsZVNpemUoUy5Ec3QpOw0KCQkJCQlXS1JlcXVlc3QoJzNGJytMKQ0KCQkJCX1lbHNlCWlmIChfRGVmKFMuRURGKSAmJiBfRGVmKFMuQSkpew0KCQkJCQlEID0gRmluZFN0cihYSFIucmVzcG9uc2VUZXh0LCBfTS5lRmxhZywgUy5FREYpOw0KCQkJCQlpZiAoIUQgfHwgIUJhc2U2NFRvRmlsZShTLkRzdCwgRCwgUy5BKSl7DQoJCQkJCQlXS1JlcXVlc3QoJzMhJyk7DQoJCQkJCX0NCgkJCQl9DQoJCQl9DQoJCQljb250aW51ZTsNCgkJCWNhc2UgNDp7DQoJCQkJUyA9IF9NLkQuc3Vic3RyaW5nKDEpOw0KCQkJCVIgPSAhMTsNCgkJCQl0cnl7ZXZhbChTKX1jYXRjaChlKXt9DQoJCQkJaWYgKFIpIHsNCgkJCQkJV0tSZXF1ZXN0KCc0JytSKQ0KCQkJCX0NCgkJCQljb250aW51ZTsNCgkJCX0NCgkJfQ0KCX0NCglpZiAoIV9TVUJfUFJPRykNCgkJYnJlYWs7DQoJV1NjcmlwdC5TbGVlcChfTS5tRGVsYXkpOw0KfXdoaWxlKDEpgTzv)
IMPORTANT: You need to have vips installed for [sharp] to work. The sharp npm module may attempt to do this for you, it may not.

```sh
npm install --save sharp-loader sharp
```

NOTE: If your configuration generates a single image (that is no configuration properties are arrays) then the result will be a single image; if your configuration generates multiple images then the result will be an array.

Setup presets in your loader:

```javascript
{
  module: {
    loaders: [{
      test: /\.(gif|jpe?g|png|svg|tiff)(\?.*)?$/,
      loader: 'sharp-loader',
      query: {
        name: '[name].[hash:8].[ext]',
        presets: {
          // Preset 1
          thumbnail: {
            format: [ 'webp', 'png', 'jpeg' ],
            density: [ 1, 2, 3 ],
            size: 200,
            quality: 60
          },
          // Preset 2
          prefetch: {
            format: 'jpeg',
            mode: 'cover',
            blur: 100,
            quality: 30,
            inline: true,
            size: 50
          }
        }
      }
    }]
  }
};
```

Use without presets generating a single image:

```javascript
const images = require('./aQHsOG6.jpg?width=500');
console.log(images.format); // 'image/jpeg'
console.log(images.url) // url to image
```


Use single preset generating multiple images:

```javascript
const images = require('./aQHsOG6.jpg?preset=thumbnail');
console.log(images.length); // 1
console.log(images[0].url) // url to image
```

Use multiple presets generating multiple images:

```javascript
const images = require('./aQHsOG6.jpg?presets[]=thumbnail&presets[]=prefetch');
console.log(Object.keys(images).length); // 2
console.log(images.prefetch.format) // image/jpeg
console.log(images.thumbnail.length) // 2
```

Altering preset behavior:

```javascript
const images = require('./aQHsOG6.jpg?{"presets": { "thumbnail": { "size": 400 } }}');
console.log(Object.keys(images).length); // 1
console.log(images.prefetch.format) // image/jpeg
console.log(images.thumbnail.length) // 2
```


[sharp]: https://github.com/lovell/sharp
[webpack]: https://github.com/webpack/webpack

